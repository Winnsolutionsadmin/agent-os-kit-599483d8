# Development Strategy (09-infra artifact 4 of 5)

**Authored:** 2026-07-08, infra-clickup session
**Scope:** repo strategy, environments, the wiggum-loop dev model, CI/CD, testing (including gate-invariant tests), instrumentation plumbing, security baseline, capacity honesty.
**Sources:** 07-roadmap/ROADMAP.md loop model + W3 loop.md, W7 instrumentation-spec, product-law-enforcement.md (artifact 2), counsel blind spot 3, doctrine (repo owns code; ClickUp owns progress; Drive owns knowledge).
**Lineage legend:** MEASURED / SURVEY / VENDOR / [unverified].

---

## 1. Repo strategy

- **This repo (agent-os-foundation) is the foundation corpus, never the product codebase.** Roadmap backlogs, decisions, research, and strategy live here; code does not.
- **The product code repo is born via /newproject-trio at the FIRST product commit** (W3.5): repo + ClickUp list + Drive folder created as one decision. The founder names the slug; until then the product is UNNAMED and no name strings appear in code, configs, or UI copy (W3 loop law).
- Spike artifacts before that first product commit live on this repo's `ws/w3-front-door` branch, then graduate.
- Consolidated estate libraries (the-sage scoring core, capture pipeline) are wrapped in place first; extraction into the product repo happens per build-sequence.md phase, each extraction traced to a W5/W3 backlog row. Estate IP treatment (license vs assignment) is W2.4, counsel-gated; engineering does not preempt it by copying code across the boundary before that call.
- One product repo until scale forces otherwise; services separate by module boundary, not by repo, at this team size.

## 2. Environment strategy (three rungs)

1. **Estate-hosted pilot (now through pilot):** single design partner, dedicated segregated instance + keys (data-governance-architecture.md section 2). Cheap, auditable in one meeting, honest about what it is; the pilot terms disclose the hosting posture.
2. **Partner-isolated (on demand):** deployment into a partner's own cloud tenancy where their security posture requires it; priced into that contract, never speculative. Bedrock/Vertex routing available as the procurement lever (VENDOR parity pricing for Claude on Bedrock).
3. **Multi-tenant V1 (month 3+):** schema-per-tenant + RLS platform per the governance architecture; staging + production split appears here, not before. Production deploys carry a founder gate; staging deploys continuously.

Environment promotion is one-way: nothing developed against real partner data locally; developers work on synthetic fixtures and the estate's own data.

## 3. The wiggum-loop dev model (how build work actually runs)

Carried from 07-roadmap: work executes as per-workstream loops, and the same model governs product code.

- **Loop prompt:** each loop has a written prompt naming its branch, backlog file, constraints, and laws (see W3-front-door/loop.md as the template). Loops pick the TOP UNBLOCKED task, build the artifact, commit with the workstream prefix, update the backlog row, push.
- **Done criteria:** each workstream's tasks.md carries explicit done criteria; a loop iteration that cannot meet them updates status honestly instead of claiming done. Proof over narration: done = sha, artifact path, or it is not done.
- **Human gates:** rows carry named gates (FOUNDER / counsel / founder review). Loops never close gated rows; they stage the artifact and mark it awaiting the gate. Money, legal, and anything sent externally is a hard stop (W2 rule generalized).
- **One executor per branch:** exactly one session owns a `ws/*` or product branch at a time (doctrine plan-executor lock). A second session on the same scope adopts the VERIFIER role: hunt gaps, never duplicate edits.
- **Liveness pulses:** commit per iteration; a silent iteration is breakage (W3 loop law). Long-running loops post state changes to the ClickUp subtask (started / blocked / decision / done), nothing else.
- **Board sync:** backlog-first commits, then ClickUp mirror (07-roadmap/clickup-structure.md protocol). The board is where cross-session state lives; the conversation is disposable.

## 4. CI/CD posture

- GitHub private repo, branch protection on main, review required (self-review ritual plus verifier session at this team size; a second human reviewer is a hiring-dependent upgrade, flagged honestly).
- CI on every push: lint, type check, unit tests, gate-invariant suite (section 6), cross-tenant leak tests, secret scan, em-dash check on client-facing artifact templates.
- Artifacts: containers tagged by commit sha. CD: staging auto-deploys from main; production is a founder-gated manual promote with automatic rollback on error-rate spike. Canary staging (5% -> 25% -> 100%) becomes real when there is more than one tenant to canary across; before that it is a deploy script, honestly named.
- The deploy gate is itself a decision class (`deploy.production`) in the gate service once the product runs: the same machinery that gates agent actions gates releases. NEVER-GRADUATE.

## 5. Instrumentation plumbing

- **One event stream, three consumers** (instrumentation law 1): W8 threshold evaluation, W10 achievement ledger, W4 scoring (day 31+). No consumer gets a private, differently-counted stream.
- Implementation: every service emits typed events (E1-E34 working identifiers from instrumentation-spec) to an append-only events table; consumers are readers, never writers of the stream. The immutable audit log (product-law-enforcement.md section 5) is the same substrate with stricter retention.
- Ledger writes: the E31/E30/E32-E34 to ledger-entry mapping in instrumentation-spec section 6 is implemented as a projector job over the stream; ledger entries are PROPOSED and founder-confirmed, never auto-published.
- Estate data source available now: Claude Code's native OTel metrics (tokens, cost, LOC, per-agent attribution) feed token-burn-vs-output scoring without new collection work (pai-observatory survey, MEASURED availability, [unverified] fitness until wired).
- Silence detection: a designated meeting with no E2 within its window auto-emits E3 (incident-grade). Monitoring watches for the ABSENCE of expected events, not just errors.

## 6. Testing strategy

1. **Gate-invariant tests (the non-negotiable suite, runs on every commit):** the six obligations in product-law-enforcement.md section 9: no side-effect path outside the executor; refusal matrix (missing/wrong/expired/replayed token, payload mismatch) each writing E10; NEVER-GRADUATE immutability; graduation property tests (no early graduation, demotion on disagreement, version reset); triage-failure escalation with zero dropped items; gate-service-down = executor refuses all while surfacing continues.
2. **Cross-tenant leak tests:** synthetic two-tenant fixture; any cross-tenant row visible = build fails.
3. **Event-stream contract tests:** every E-event schema versioned; consumers pinned to schema versions; a producer schema change without consumer migration fails CI.
4. **Scoring determinism tests:** same event sequence in = same scores out (W4 anti-abuse rules included), so partner-facing numbers are reproducible; honest math requires replayability.
5. **Capture pipeline regression:** the known dedup bug (7/8 call landed 3x, MEASURED) gets a regression test before any second tenant; dedup failures compound with tenant count.
6. **Standard pyramid** under all of it: unit on scoring/graduation math, integration on adapter + capture, thin E2E on the front-door approve/edit/skip loop.

## 7. Security baseline (engineering-side; governance-side in artifact 3)

- No secrets in code; secret manager from the first product commit; scoped credentials so side-effecting keys exist only inside the Action Executor boundary.
- Dependency and container scanning in CI; MCP servers we ship get their own security review before any client credential flows through them (30+ MCP CVEs Jan-Feb 2026, VENDOR/press; "it's MCP" is necessary, not sufficient).
- OAuth/API-key audit of the estate fleet before partner data flows (enterprise-deployment.md finding B; consumer-OAuth enforcement precedent Jan 2026).
- Untrusted-content discipline as a code pattern: transcript-derived text never interpolates into tool-executing prompts without the isolation layer.

## 8. Capacity plan honesty (counsel blind spot 3)

- **The estate is a single-operator system.** Jarred is founder, GTM, delivery, AND the fleet operator; Carter's engineering capacity is contribution-based and not yet contracted (W2 framework pending); Nick's scope is design, not build.
- Known collision (overview grey area 13): Anchorage Sprint 1 (7/9-19) overlaps the 7/11 shared doc, 7/15 concept doc + deck, and 7/17-18 meeting. The build plan therefore front-loads only ONE engineering artifact before 7/15: the W3 read-only spike. Everything else pre-7/15 is authored strategy, not code, on purpose.
- Loop-based development is the capacity multiplier the estate already runs (MEASURED at fleet-of-one scale), but human-gate throughput is the binding constraint: every founder gate consumes Jarred-attention. Gate batching (daily review block) is the working default; the pilot's B3 metric (attention cost) applies to our own operation too.
- Hiring/delegation triggers, stated honestly: a signed pilot (the raise trigger) plus month-2 productization load is the point where single-operator + contribution engineering stops being credible; the founder operating model one-pager (W2.5) owns the plan. Until then, scope discipline IS the capacity plan.
- Named legal/compliance owner: does not exist yet (blind spot 3); W2.3 must name one. Engineering treats "counsel-gated" as blocked until that owner exists.

## 9. Needs founder

1. Approve the daily gate-batching default (one founder review block per day) vs ad-hoc interrupts.
2. W2.4 estate-IP call before any estate library code crosses into the product repo (engineering is sequenced to not need it before then, but the call is on the critical path of phase 2 in build-sequence.md).
3. Second-human code review: accept verifier-session review as the interim standard, or name a human reviewer.
