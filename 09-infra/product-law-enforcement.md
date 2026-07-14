# Product Law Enforcement: How the Gates Are Implemented (09-infra artifact 2 of 5)

**Authored:** 2026-07-08, infra-clickup session
**The law (counsel: "don't touch it"):** never auto-act on money, irreversible, or external actions without a human gate; autonomy is earned via graduation: 90% agreement over 20+ reps per decision class.
**Sources:** 01-overview section 5 (must-haves 1-7), command-center shelved calibration design (Tier B evidence), W7 instrumentation-spec events E8-E10/E34, W7 days-1-30 plan, W3 loop constraints.
**Design stance:** the law is enforced by ARCHITECTURE, not by prompt discipline. An agent that wants to violate it must defeat a service boundary, not ignore an instruction.

---

## 1. The hard invariant

**Zero ungated money / irreversible / external actions.** Formally: every side-effecting action executes through exactly one path, the Action Executor, and the Action Executor refuses any request lacking a valid gate token for the action's decision class. There is no second path. Agents never hold credentials that can produce a gated side effect directly; credentials for money-moving, destructive, or external-facing operations live only inside the executor's boundary.

The invariant is COMPUTED, not asserted (instrumentation law 4): the day-30 zero-ungated attestation is `count(E10) = 0` over the phase, derived from the event stream. If the stream cannot prove it, it does not exist.

## 2. Gate service

The single choke point between "agent proposes" and "world changes."

- **Input:** an execution proposal (E8 `workflow.execution.proposed`): decision class, action payload, initiating agent/session, tenant, evidence refs.
- **Classification:** every proposal maps to exactly one decision class via the registry (section 3). Unclassifiable proposals are gated at the strictest level by default; unknown = gated, always.
- **Resolution:** a human decision card (Approve / Edit / Reject) on the front-door or operator surface. Resolution emits E9 `workflow.gate.decided` with decision class, outcome, agreement flag, and latency.
- **Token issue:** approval mints a single-use, class-scoped, payload-hash-bound gate token with a short TTL. The executor validates token, class, and payload hash; any mismatch is a refusal plus an E10 event.
- **Graduated classes:** if (and only if) a class has GRADUATED (section 4), the gate service may auto-approve for that class, and it still writes E9 with `auto=true` plus the full audit record. Graduation changes who approves, never whether the record is written.

## 3. Decision-class registry

- A decision class is a named, versioned definition: action category, blast radius (money amount bands, reversibility, external visibility), tenant scope, and required approver role.
- Seed taxonomy (pilot): `capture.scope_change`, `artifact.external_send`, `task.create_in_partner_tool`, `commitment.close`, `money.any` (never graduates below founder gate), `irreversible.any`, plus the ONE pilot workflow's specific classes chosen in week 1 (E25 `workflow.selected`).
- Registry changes are themselves gated (class: `registry.change`, human-only, never graduates) and versioned; graduation stats never carry across class-definition versions. Editing a class resets its ledger to zero reps.
- Three classes are marked NEVER-GRADUATE at the schema level, not by convention: `money.any`, `irreversible.any`, `external.any` above their de-minimis definitions. The graduation machinery is structurally unable to flip these to auto-act. Product law says autonomy is earned; it does not say every class is earnable.

## 4. Graduation ledger

- **The math lives in one place** and computes exclusively from E9 events: agreement rate per (decision class, class version) over resolved reps. Threshold: >= 90% agreement over >= 20 reps.
- **Conservative agreement semantics: edit = disagreement.** Approve-without-edit is the only outcome that counts as agreement; Edit and Reject both count against. This is the conservative read proposed in instrumentation-spec open item 3 and adopted here as the working rule. NEEDS FOUNDER confirmation before pilot day 1; if Jarred wants weighted partial credit for edits, only the ledger function changes, no schema change.
- **Windowing:** the 20+ reps are consecutive-trailing, not lifetime-cherry-picked; a post-graduation disagreement (human overrides an auto-acted item, or an audit flags one) demotes the class immediately back to gated and restarts its window. Demotion is cheap and carries no ceremony; re-graduation requires the full 90%/20 again.
- **Ledger record per class:** reps, agreements, current rate, status (gated / graduated / demoted / never-graduate), version, last transition, evidence refs. Readable in the operator console; per-class status also surfaces on the partner-facing weekly attestation (E24) so graduation is never invisible to the client.

## 5. Immutable audit log

- Append-only event log; every E8/E9/E10/E34 record plus every executor invocation writes to it. No update or delete path exists in the application layer; corrections are new events referencing the corrected one.
- Implementation posture: Postgres append-only table (revoked UPDATE/DELETE at the role level) shipping to object-storage archive; hash-chained batches so tampering is detectable. Signature hardening (per-agent signing keys) is the attribution pillar's future work; the event shape (initiator, approver, executor, tenant, timestamps, payload hash) is designed now so proof-of-origination later needs no rework.
- The audit log is the source for: zero-ungated attestation, graduation evidence, achievement-ledger entries (W10), and any client security review.

## 6. Fail-open surfacing (must-have 2)

"Fail open" means fail open TO THE HUMAN, never to execution:

- Decisions, money, deadlines, and irreversible items must never be suppressed by a triage layer. If the translator/triage layer errors, times out, or is uncertain, the item escalates to the human raw rather than being dropped or silently deferred.
- If the gate service itself is down, the Action Executor refuses everything (fail CLOSED for actions) while the surfacing pipeline continues delivering pending items (fail OPEN for visibility). Both halves are explicit design requirements, tested (dev-strategy.md section 6).
- E10 `workflow.ungated_attempt` is sev-1: the workflow pauses, an incident is recorded, the executive is informed (days-1-30 plan section 5). An E10 is never quietly retried.

## 7. Kill criterion (E34)

- One falsifiable sentence, written and signed with the baseline package before day 1 (instrumentation-spec section 4 item 5).
- Formally evaluated at day 30 and on any trigger; outcome recorded as E34. A clean stop is ledger-worthy (an honest stop entry in the W10 achievement ledger); the machinery must make stopping cheap, not shameful.
- The weekly attestation (E24) includes a kill-criterion glance so the evaluation is never a surprise.

## 8. Demo-time law (W3)

The 7/17-18 demo is read-only by founder decision, so no gated action can fire in the room. Anything shown that LOOKS like an action (a decision card, an approval) is either live-read-only or explicitly labeled a mock. Product law visible in the demo itself: any money/irreversible/external action shown sits BEHIND a human gate on screen.

## 9. Gate-invariant test obligations (enforced in CI, defined in dev-strategy.md)

1. No code path outside the Action Executor can reach side-effecting credentials (static check + secret-scope audit).
2. Executor refuses: missing token, wrong class, payload-hash mismatch, expired token, replayed token. Each refusal writes E10.
3. NEVER-GRADUATE classes cannot be flipped by any API surface, including admin.
4. Graduation function property tests: no sequence of fewer than 20 reps graduates; any post-graduation disagreement demotes; class-version edit resets reps.
5. Triage-failure injection: translator outage escalates items raw; zero items dropped.
6. Gate-service outage: all executor calls refuse; surfacing continues.

## 10. Needs founder

1. Edit-as-full-disagreement graduation semantics (section 4): confirm or specify weighting.
2. De-minimis definitions for `external.any` (e.g. does an internal-only ClickUp comment in the partner workspace count as external?). Proposed default: anything visible to a non-operator human is external until Jarred narrows it.
3. Whether graduated auto-acts appear on the partner weekly attestation individually or as class-level counts (proposed: class-level counts with drill-down available).
