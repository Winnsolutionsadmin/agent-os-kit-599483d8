# Build Sequence: Dependency-Ordered Plan on the Pilot Timeline (09-infra artifact 5 of 5)

**Authored:** 2026-07-08, infra-clickup session
**Timeline spine:** spike pre-7/15 -> pilot days 1-30 (capture + ONE gated workflow) -> days 31-90 (gamification entry) -> months 2-6 (productization to V1). Pilot day 1 starts at E31 (signed design-partner pilot, THE raise trigger) and is calendar-unknown until Jarred signs a partner; phases below are pilot-relative.
**Traceability rule:** every build item names the workstream backlog row it serves. Nothing gets built that no backlog row asked for.
**Lineage legend:** MEASURED / SURVEY / VENDOR / [unverified]. All duration estimates below are [unverified] planning figures until a technical sizing pass with Carter (architecture-consolidation.md flagged effort sizing as out of scope; that remains true).

---

## Phase 0: Spike (now through 7/15; demo 7/17-18)

The ONLY code phase before 7/15, on purpose (capacity honesty, dev-strategy.md section 8).

| # | Build item | Traces to | Depends on | Definition of done |
|---|---|---|---|---|
| 0.1 | exec-gui answer-relay spike, read-only | W3.2 | founder scope decision (done, 262b130) | A running two-pane surface that relays real answers from a live estate session; zero action paths |
| 0.2 | Wire spike to one real estate surface (fleet HUD or OKR readout) | W3.3 | 0.1 | Live data renders in the workspace pane from the chosen surface, read-only, stable for a 15-minute demo |
| 0.3 | Demo script | W3.4 | 0.2 | What Jarred clicks, what it shows, what it proves; product law visible on screen; FOUNDER review passed |

Phase gate: Jarred can drive the demo without a rehearsal crutch (W3 done criterion). No mock passed off as live; anything mocked is labeled.

## Phase 1: Pilot foundation (contract signature through day 30)

Scope law (W7.1): capture + ONE gated workflow. Nothing else enters.

| # | Build item | Traces to | Depends on | Definition of done |
|---|---|---|---|---|
| 1.1 | Segregated pilot deployment (instance + keys, partner data walled from estate) | W9.2 pilot posture | W9.1 draft (artifact 3 section 2) | Partner security can verify segregation in one meeting; hosting posture disclosed in pilot terms (W7.4) |
| 1.2 | Event stream v0 (append-only store + E1-E14, E20-E25 emitters) | W7.3 | 1.1 | One stream, consumers read-only; baseline events (E20-E23) recordable before day 1 |
| 1.3 | Capture pipeline wrapped for the partner (consolidation, not rewrite) + dedup regression test | W7.1, W5.1 source pattern | 1.1; W9.3 pilot consent posture (FOUNDER gate) | Designated meetings captured; E3 fires on a missed one (silence = breakage); dedup test green; hard-wall exclusions enforced |
| 1.4 | Gate service v0 + decision-class registry seed + Action Executor boundary | product-law-enforcement.md sections 2-3 | 1.2 | Gate-invariant test suite green (dev-strategy.md section 6.1); E8/E9/E10 flowing; NEVER-GRADUATE classes locked |
| 1.5 | THE one gated workflow, selected week 1 by rubric (E25) | W7.1 | 1.3, 1.4 | 15+ gated executions by day 30; count(E10) = 0 computed from the stream |
| 1.6 | Graduation ledger v0 (read-only reporting; no auto-act in phase 1) | product-law-enforcement.md section 4 | 1.4 | Per-class agreement rates visible; edit-=-disagreement semantics implemented pending founder confirm |
| 1.7 | Weekly attestation surface (E24) + kill-criterion glance (E34 machinery) | W7.1 section 5 | 1.2 | Weekly check-in runs off live data; day-30 gate evaluation (E30) is a query, not an assembly job |

Phase gate (day 30, from buyer-roi-model.md, all threshold numbers [unverified] candidates until the partner signs the baseline): capture coverage 90%+; 15+ gated executions with ZERO ungated (zero is hard); baselines signed; B2 trending down. Kill criterion formally evaluated.

## Phase 2: Gamification entry (days 31-90)

Blocked on TWO gates: the day-30 evidence gate AND Nick's mechanics spec (7/31, EXTERNAL).

| # | Build item | Traces to | Depends on | Definition of done |
|---|---|---|---|---|
| 2.1 | Ingest Nick's mechanics; synthesize anti-abuse design | W4.1, W4.2 | Nick 7/31 | Leagues/caps/outlier/role-adjust rules written as testable rules, Nick author of record |
| 2.2 | Scoring engine v0: per-person data model + E15-E18 emitters, opt-in only | W4.3, W4.4 | 2.1; W9.3 consent text (FOUNDER gate) | Comp-decoupled at code level; scoring determinism tests green; opt-out honored forward |
| 2.3 | Achievement ledger projector (event stream -> PROPOSED ledger entries) | W10.2 | 1.2 | Day-30/60/90 gate entries generate from E30 automatically; founder confirms before publish |
| 2.4 | OKR engine documentation + org tree schema drafting (build starts, no partner cutover) | W5.1, W5.2 | none (parallel track) | the-sage pattern documented as it runs; multi-tenant schema reviewed |
| 2.5 | Estate-IP boundary execution per W2.4 counsel call | W2.4 | counsel + founder gate | Library code crosses into the product repo only under the decided license/assignment terms |

Phase gate (day 60/90, [unverified] candidates): adoption 60%+ weekly active among opt-ins; B1 3+ hours/week recovered; B2 down 50%+; graduation progress visible per class; day-90 B3 client-MEASURED.

## Phase 3: Productization to V1 (months 2-6)

| # | Build item | Traces to | Depends on | Definition of done |
|---|---|---|---|---|
| 3.1 | Multi-tenant substrate: schema-per-tenant + RLS + per-tenant keys + quotas | W9.2 V1 posture | phase 1 running | Cross-tenant leak tests green; second tenant onboardable without bespoke work |
| 3.2 | Front-door V1: multi-user web app (two-pane, intent bar, decision cards, SSO) | W3.5 graduation; scorecard gap (a) | 3.1; /newproject-trio repo birth (founder names slug) | A partner user other than the executive completes the approve/edit/skip loop over SSO |
| 3.3 | OKR engine productized: org tree live, weighted subtask mapping, outcome scoring spec to W4 | W5.2-W5.4 | 2.4, 3.1 | Partner org OKR tree drives agent task weighting; outcome axis has a named real data source (must-have 17) |
| 3.4 | PM-tool adapter v1: ClickUp connector (public API only) behind the agnostic interface | W5.5 | 3.3 | No vendor SDK imports outside the adapter; second-connector build triggers only on partner demand (counsel verdict 7) |
| 3.5 | Gamification hardening: leagues + anti-abuse at org scale | W4.2-W4.4 | 2.2 at pilot scale | Anti-abuse rules fire on synthetic abuse fixtures; weekly cap-hit review operative |
| 3.6 | Multi-model abstraction in production + first quarterly open-weight fire drill | architecture-overview.md 3.8 | 3.1 | Swap test executed and logged; drill calendarized |
| 3.7 | Governance V1: retention automation, breach playbook, vendor-review cadence, audit-log export | W9.3, W9.4 | 3.1 | Governance one-pager survives a partner security meeting (W9 done criterion) |
| 3.8 | Observability: per-tenant golden signals + token budget caps + cost attribution | architecture-overview.md 3.6 gap list | 3.1 | Budget cap pauses a runaway tenant workload automatically; cost per tenant reportable |

Phase gate: second design partner onboardable (domino 2, engineers) without founder heroics; raise-support evidence accumulating in the ledger; SOC 2 formal audit kickoff decision on first enterprise deal (counsel verdict 6).

## Explicitly NOT in this sequence

- **Attribution pillar build** (W-INFRA future wedge): audit-log event shape is attribution-ready (product-law-enforcement.md section 5); no dedicated build until it earns a backlog row. Counsel verdict 10.
- **Skill marketplace monetization:** parked with tokenization per counsel; registry/discovery earns a row only post-V1.
- **Sovereign GPU stack:** deferred (enterprise-deployment.md option 5); client-funded line item only.
- **Second PM connector:** on partner demand only.
- **Anything Mima, anything Upexi-premised, any product name.**

## Dependency spine (critical path)

```
W3 spike (0.1-0.3) -> 7/17-18 demo
E31 signed pilot -> 1.1 segregation -> 1.2 events -> {1.3 capture, 1.4 gates} -> 1.5 THE workflow -> day-30 gate
day-30 gate + Nick 7/31 -> 2.1 -> 2.2 scoring -> day-60/90 gates
W2.4 IP call -> 2.5 -> 3.2/3.3 productization
3.1 multi-tenant -> everything in phase 3
```

Single most schedule-fragile external input: Nick's 7/31 mechanics (phase 2 head). Single most schedule-fragile internal gate: W9.3 founder review of consent posture (blocks capture beyond the executive's own desk, instrumentation-spec section 5).

## Needs founder

1. Sign-off on this phase structure feeding the W7.4 pilot terms (phases are contract-visible).
2. The three founder gates on the critical path, batched for one sitting if possible: E9 edit semantics, W9.3 consent posture, gate-batching cadence.
