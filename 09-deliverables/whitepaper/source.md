# [NAME]
#### Technical whitepaper: a governed control loop for agent work inside an organization

*[NAME] is a deliberate placeholder. The product is intentionally unnamed; the permanent mark is chosen last, from a legally cleared shortlist, after the position is locked. The brackets are the design, not a gap. The working descriptor is an agent OS for organizations, used sparingly and never as a name. Founder: Jarred Winn. Document date: 2026-07-09.*

---

## Abstract

Enterprises do not lack AI capability. They lack a way to let a whole organization use that capability without losing control of it. This document specifies the system we are building to close that gap: a single conversational front door over a governed control loop that observes a company's real events, proposes work against stated objectives, and executes only what a human authorizes, with autonomy earned per class of decision rather than assumed.

It is written for an engineering leader, not a buyer. It is honest about what runs today and what is still design. A reference implementation, operated by the founder at the scale of one person directing many agents, already runs the observe-and-propose half of the loop in production. The gate, the executor, the graduation ledger, and the multi-tenant substrate are specified here and are the real build. Every capability in this document carries a build-status label, and every number carries an evidence tag. Nothing designed but unbuilt is written in the present tense.

The claim is narrow and, we think, defensible: the moat is not the model. It is the organizational psychology of adoption and the governance that makes agent work safe to run. This paper describes the mechanics of both.

---

## Legend

Read every claim in this document through two labels.

**Build status** (what is real today):

- `[ BUILT ]` The capability runs in the reference implementation today. Present tense is allowed.
- `[ PROTOTYPE ]` A validated spike exists, not deployed.
- `[ PILOT-SCOPE ]` Specified and scheduled for the first design-partner build. Described in design tense only.
- `[ HORIZON ]` A future wedge. No build now.

**Evidence lineage** (how a number is known):

- `MEASURED` read from live telemetry in the reference implementation.
- `SURVEY` a cited third-party study.
- `VENDOR` a vendor or press term of record.
- `[unverified]` an internal estimate or a proposed default not yet confirmed.

The reference implementation is a reference implementation. It is operated by the founder to prove the pattern. It is not an installed customer, and no count in it is customer traction.

---

## 1. The pain this is about

Start inside a company that has already "adopted AI." The adoption is real and it is a mess. Every team bought its own tools. Meeting bots join calls that nobody sanctioned. The decisions made in those meetings evaporate into a recap email that nobody reads, and the work they implied never gets built. The company's objectives live in a quarterly deck that has no wire connecting it to what people did this week. And the employees who use AI best are the ones hiding it, because disclosing it is punished.

None of that is hypothetical, and the team building this has lived the sharp end of it. While assembling this launch kit, the operator of the reference implementation found more than a dozen undisclosed meeting-capture bots embedded across the estate's own Google and Zoom accounts, some with standing calendar access, and had to forensically evict them across several sessions (MEASURED, internal history, 2026-07-06 to 2026-07-08). That is shadow-AI sprawl inside a single disciplined operator's accounts. Multiply it by a workforce that was never given a sanctioned path, and you have the real starting condition of most "AI-forward" companies.

Named plainly, the pains are five:

1. **Sprawl without control.** Tools, bots, and agents proliferate faster than anyone governs them. The undisclosed-notetaker incident above is one operator's version of a company-wide problem.
2. **Meetings that decide nothing that ships.** Work is agreed in a room and then lost between the room and the tools where work actually happens.
3. **Objectives disconnected from execution.** A North Star in a deck cannot tell you whether today's work moved it.
4. **Fear that suppresses the exact behavior adoption needs.** 94 percent of knowledge workers already use AI at work, yet in a controlled study a colleague who disclosed using it was rated 10x lazier and 24 points less likely to be picked for a high-visibility project, at identical output (SURVEY, Atlassian 2026). The behavior a company most needs to see is the behavior its own culture drives underground.
5. **No trace.** On the rare occasion an agent does act, no one can reconstruct what it saw, why it acted, or who let it. Without a trace there is no trust, and without trust there is no mandate to let it act again.

The cost of doing nothing is not zero. It is sprawl that compounds, a culture that hides its own best practice, and a growing surface of automated actions that no one can account for. A company in this state does not need more capability. It needs a container.

---

## 2. The thesis: capability is arriving, adoption is not

The capability to do agent work well is arriving on schedule from the frontier labs. We concede that plainly, because it is the premise of the whole business rather than a threat to it. The labs will keep shipping stronger models and better agent frameworks. What no lab has claimed, and what no model release closes, is the distance between a capability existing and a whole organization actually using it under control.

The measured shape of that distance: 62 percent of organizations are experimenting with agents, roughly 23 percent have scaled even one system into production, and full agentic operation is rarer still (SURVEY, McKinsey Nov 2025). The gap between experimenting and operating is not a model gap. It is an organizational one. It is the five pains in section 1, and every one of them is a problem of psychology, governance, and workflow rather than of raw capability.

This reframes what the product is. The product is not a smarter agent. It is the layer that lets an organization put agents to work without the sprawl, the fear, and the missing trace. Concretely, that layer is three things braided together:

- **Organizational psychology.** Adoption is driven by rewarding people for using AI, not by threatening to replace them. This is the difference between a workforce that hides its AI use and one that competes to show it. Section 6 specifies the mechanics.
- **Governance made visible as product behavior.** The system earns the right to act. It cites its sources, distinguishes what it observed from what it inferred, exposes uncertainty, and refuses to act outside its authority. Trust is not a brand adjective here; it is the observable behavior of the control loop in section 3.
- **Consultative delivery.** This is not an out-of-the-box install. It is an in-the-box system that requires out-of-box configuration per business, delivered as a consulting-plus-software hybrid. Legacy integration is real friction, not magic, and the consultative companion is the bridge across it.

One metric sits above the others: the compression of time between thought and output. Everything the system does is downstream of that. An objective becomes work faster; a decision made in a meeting becomes a shipped task faster; a routine choice stops consuming a person's attention. The governance exists so that this compression never comes at the price of an action no one authorized.

We do not claim immunity from the frontier labs. A lab could build this. The bet is that the hard part is not the part a lab is racing to build. The hard part is getting a specific company's people to trust and use the thing, and that is earned per organization, on the ground, with the mechanics below.

---

## 3. The control loop

Everything the system does is one loop, run over and over, per event. The loop has eight steps. The first three are observation and proposal; the middle two are the human gate and the single execution path; the last three are how the system checks its own work and how authority is earned and taken back.

```
   observe -> contextualize -> propose -> [ GATE ] -> execute -> verify -> learn
      ^                                       |                              |
      |                                       +-- human holds this ----------+
      +---------------------- revoke <--- authority is reversible -----------+
```

**1. Observe.** A source event enters the system: a captured meeting, a webhook from the work tracker, a message, a scheduled check. `[ BUILT ]` in the reference implementation, the capture pipeline ingests meetings today and turns them into structured notes, decisions, and action items.

**2. Contextualize.** The system retrieves what bears on the event: relevant memory, the objective tree, prior decisions, contact records. Each retrieved item is stamped with its source and its age, and the system narrates only the data path it actually traversed. It does not smooth over a gap; it marks it. `[ BUILT ]` for retrieval and provenance in the reference implementation; the objective tree is `[ BUILT ]` as a personal tool and `[ PILOT-SCOPE ]` as an org-shaped, multi-tenant structure.

**3. Propose.** An agent produces a recommendation, not an action. The proposal is typed. It carries a decision class, the exact payload that would change the world if approved, the initiating session and tenant, and references to the evidence it used. A proposal is a request to act, and it is inert until a gate resolves it. `[ PILOT-SCOPE ]`.

**4. Gate.** The proposal reaches a human as a decision card with three moves: Approve, Edit, Reject. The gate classifies every proposal into exactly one decision class; an unclassifiable proposal is gated at the strictest level, because unknown means gated, always. Nothing that touches money, an outside party, or anything irreversible passes this step without a person deciding. This is the step the human holds, and can always take back. `[ PILOT-SCOPE ]`; the two-pane interaction and Approve/Edit/Skip pattern exist as `[ PROTOTYPE ]` from the operator console.

**5. Execute where authorized.** On approval, a single service, the Action Executor, performs the side effect. It is the only path to a side effect in the entire system. It refuses any request that lacks a valid, single-use, class-scoped token bound to the exact payload that was approved. Agents never hold the credentials that move money or reach an outside party; those credentials live only inside the executor's boundary. An agent that wanted to act on its own would have to defeat a service boundary, not ignore an instruction. `[ PILOT-SCOPE ]`.

**6. Verify.** The outcome is scored against the objective it was meant to serve, and an audit receipt is written: what changed, who approved, how long it took. The receipt is append-only. `[ BUILT ]` for objective scoring in the reference implementation (activity alignment; outcome movement needs a real key-result data source before it is more than a vanity number); `[ PILOT-SCOPE ]` for the audit receipt as a product surface.

**7. Learn.** The system records whether its recommendation matched the human's actual choice, per decision class. Agreement accrues only where a human approved without editing. This is the raw material of earned autonomy, specified in section 5. `[ PILOT-SCOPE ]`.

**8. Revoke.** Authority is reversible by construction. A class that earned the right to act loses it the moment a human overrides an auto-acted item or an audit flags one; it drops back to a full human gate and has to earn the right again from zero. Demotion is cheap and carries no ceremony. `[ PILOT-SCOPE ]`.

### 3.1 One event, end to end

An engineer should be able to follow a single event through the whole loop. Here is one, with each rung's build status inline so the trace is honest about what runs and what is designed.

A recurring vendor-renewal meeting is captured (**observe**; `[ BUILT ]`). The system retrieves the vendor's current terms, the last three decisions about this vendor, and the objective this spend rolls up to, each item stamped with its source and how old it is (**contextualize**; `[ BUILT ]`). An agent drafts a short email declining the renewal and proposes it as a task of class `external.send`, attaching the draft, the vendor record it read, and the objective reference (**propose**; `[ PILOT-SCOPE ]`). Because `external.send` is a class that never graduates, the draft arrives as a decision card; the executive reads it, edits one sentence, and approves (**gate**; `[ PILOT-SCOPE ]`). Only on that approval does the executor send, validating a one-time token bound to the exact edited message and refusing anything else (**execute**; `[ PILOT-SCOPE ]`). The send, its approver, the edit, and the elapsed time are written to an append-only receipt (**verify**; `[ PILOT-SCOPE ]`). Because the human edited rather than approved clean, the system counts this as a disagreement for the `external.send` class, so the class moves no closer to autonomy (**learn**; `[ PILOT-SCOPE ]`). And because `external.send` is a never-graduate class, no accumulation of agreement would ever let it act unattended anyway (**revoke / never-graduate**; `[ PILOT-SCOPE ]`). The human attention this consumed: the time to read one card and change one sentence.

That trace is the product. The compression is real (a decision made in a meeting becomes a reviewed, sent, and recorded action in minutes), and the control is real (nothing left the company without a named person approving the exact bytes). The loop is the same whether the event is a meeting, a webhook, or a scheduled check; only the class and the payload change.

---

## 4. Architecture: the reference implementation, mapped to the enterprise target

### 4.1 What runs today

The reference implementation is one person directing a fleet of agents across a working consulting operation. It runs the observe-and-propose half of the loop in production. Its operating counts are `N=1 operating evidence`, not customer traction, and they are collected in the appendix. In plain terms, today there is a native operator console that surfaces only the tiles that need a human; a capture pipeline that turns meetings into notes, decisions, and tasks; an objective-alignment scorer that maps work back to a stated objective tree; and a recognition engine that scores the operation's own output. All `[ BUILT ]`.

### 4.2 Why the code does not port, and what does

Being honest about the starting point: nothing in the reference implementation is multi-tenant-shaped (MEASURED, repo-reality scan 2026-07-08). It was built for one operator. That is a feature for proving the pattern and a liability for shipping a product, and we treat it as both.

Three of the four core pillars carry validated logic worth consolidating into libraries rather than rewriting: the objective-alignment scoring, the capture pipeline, and the recognition-engine math. The front door is the one pillar with no shipping code to consolidate; it gets built new as a multi-tenant web application. The rule across the board: the patterns migrate (the two-pane surface, the Approve/Edit/Skip card, the graduated-autonomy rule), the code does not. Anyone who claims the reference implementation is the product is selling the wrong thing.

### 4.3 The productization work, named honestly

Between the reference implementation and an enterprise-grade product sits real engineering. Naming it honestly is part of the trust case, so here it is, each item `[ PILOT-SCOPE ]` unless noted.

- **Tenancy.** The estate is single-operator. The pilot is a dedicated single-tenant deployment: the partner's data in its own database instance under its own encryption keys, physically segregated from the reference implementation from day one. The multi-tenant version is schema-per-tenant plus row-level security on every query, per-tenant keys, per-tenant budget caps, and a cross-tenant leak test in the build that fails if any query ever returns another tenant's rows.
- **Identity.** Redirect-based SSO in the browser (SAML/OIDC), never OAuth inside an embedded webview. Role-based access control in the application, with the scoring store held as its own access role separate from everything else.
- **Permissions.** The decision-class registry and the single-use, payload-bound gate token described in section 5. This is what makes "execute only what is authorized" a property of the code rather than a promise.
- **Durable execution.** The agent SDK gives sessions and tool calls. It does not give retries, per-tenant budget caps, durable execution across failures, centralized observability, or multi-tenancy. Those are the substance of the V1 build, not incidental plumbing, and we say so rather than imply the SDK ships them.
- **Integrations.** A work-tracker-agnostic adapter (tasks read and write, objective and key-result read and write, inbound webhooks, idempotent upserts keyed by external id). One connector is built first; a second is built when a design partner requires it. No product logic ever imports a vendor SDK directly; everything crosses the adapter.
- **Evaluations.** Per-client evaluation sets that measure whether the system's recommendations match that client's actual choices, per decision class. These are the input to earned autonomy and they are client-specific by design (section 7).
- **Audit.** An append-only event log with UPDATE and DELETE revoked at the database role level, shipped to an object-storage archive in hash-chained batches so tampering is detectable. It is the single source for the zero-ungated attestation, for graduation evidence, and for any client security review.
- **Incident response.** Surfacing fails open to the human: if the triage layer errors or is uncertain, the item escalates raw rather than being dropped. An attempted ungated action is a severity-one event that pauses the workflow and informs the executive; it is never quietly retried. The breach commitment is 24-hour internal and 72-hour partner notification, and tenant-aware logging makes blast-radius determination a query rather than an investigation.

### 4.4 Where each capability actually stands

An uninvolved reviewer should be able to place every visible capability without asking the founder. This table does that.

| Capability | Operating internally (N=1) | Prototype | Pilot build | Horizon |
|---|:---:|:---:|:---:|:---:|
| Meeting capture to structured notes/tasks | running | | harden for a tenant | |
| Objective-alignment scoring | running (activity axis) | | outcome axis on real KR data | |
| Recognition / achievement engine | running (single tally) | | per-person model (after mechanics spec) | |
| Operator console (fleet HUD) | running | | patterns export to front door | |
| Front door (client web app) | | read-only estate readout | multi-tenant two-pane app | |
| Gate service + decision-class registry | | | build | |
| Graduation ledger (earned autonomy) | | | build | |
| Action executor (single side-effect path) | | | build | |
| Immutable audit log as a product surface | event shape in use | | build | |
| Tenant + governance substrate | | | single-tenant segregated; then RLS | |
| Work-tracker adapter | | | first connector | second connector on demand |
| Speaker attribution | | validated, not deployed | consent-gated deploy | |
| Gamification (per-person/org) | | | after mechanics spec | rewards economy |
| Skill marketplace with per-run monetization | registry as pattern-proof | | | build |
| Attribution / proof-of-origination | | | | build |
| SOC 2 Type II | controls aligned | | | audit on first enterprise deal |

The read-only estate readout is exactly that: a live, read-only view of real estate data, with no action paths behind it. It is the honest thing to demonstrate, and it is labeled read-only wherever it appears.

---

## 5. The product law: graduated autonomy per action class

This is the part an engineering leader should read most carefully, because it is where the trust is either real or theater. The law is enforced by architecture, not by prompt discipline. Everything in this section is `[ PILOT-SCOPE ]`; the reference implementation's operator console carries the pattern, not the multi-tenant machinery.

### 5.1 The hard invariant

Zero ungated money, irreversible, or external actions. Formally: every side-effecting action executes through exactly one path, the executor, and the executor refuses any request lacking a valid gate token for the action's class. There is no second path. The invariant is computed, not asserted: the attestation that zero ungated actions occurred over a period is a count of ungated-attempt events equal to zero, derived from the event stream. If the stream cannot prove it, it did not happen.

### 5.2 The unit of governance is the action class

A decision class is a named, versioned definition: an action category, a blast radius (money bands, reversibility, external visibility), a tenant scope, and the approver role required. A seed taxonomy for a pilot includes classes like `capture.scope_change`, `artifact.external_send`, `task.create_in_partner_tool`, `commitment.close`, plus `money.any`, `irreversible.any`, and the one pilot workflow's own classes chosen in week one. Changing a class definition is itself a gated, human-only action, and it resets that class's evidence to zero, because agreement measured against one definition means nothing against another.

### 5.3 The evidence threshold

A class earns autonomy only when the system's recommendation has matched the human's actual choice at least 90 percent of the time across at least 20 resolved decisions. The 20-plus are consecutive and trailing, not cherry-picked across a lifetime. Below the threshold, every action in the class is gated to a human. This is the same 90-percent-over-20-reps rule the reference implementation's own design has carried from the start; it is deliberately conservative and deliberately boring.

### 5.4 Disagreement semantics

Only an approval with no edit counts as agreement. An Edit and a Reject both count against the class. The reasoning: an edit is the human correcting the system, and a system that needs correcting has not earned the right to skip the human. This is the conservative reading, and it is the working rule; it needs founder confirmation before the first pilot day, and if weighted partial credit for small edits is wanted later, only the ledger function changes, not the schema. We flag it as an open decision rather than pretend it is settled.

### 5.5 Sign-off and the record

Resolution happens on a human decision card. When a class has graduated, the gate service may auto-approve for that class, and it still writes the full record with an explicit auto-approved flag plus the complete audit entry. Graduation changes who approves. It never changes whether the record is written. Per-class status is visible to the client on a weekly attestation, so autonomy is never invisible to the people it acts for.

### 5.6 Revocation

Autonomy is a lease, not a grant. A single post-graduation disagreement (a human overriding an auto-acted item, or an audit flagging one) demotes the class immediately back to a full human gate and restarts its window. Re-graduation requires the whole 90-over-20 again. Demotion is cheap and unceremonious on purpose: the machinery must make taking authority back a routine act, not a confession of failure.

### 5.7 Classes that never graduate

Three classes are marked never-graduate at the schema level, not by convention: money in any amount, anything irreversible, and anything external-facing above a de-minimis definition. The graduation machinery is structurally unable to flip these to auto-act, and no API surface, including an administrator's, can override that. Product law says autonomy is earned. It does not say every class is earnable. The de-minimis lines (does an internal comment in a partner's own tool count as external?) are a founder decision; the safe default is that anything visible to a non-operator human is external until narrowed.

### 5.8 The graduation ladder

```
  MONEY / IRREVERSIBLE / EXTERNAL  ...  [ locked: never graduates, any rep count ]
  ---------------------------------------------------------------------------
  GRADUATED   >= 90% agreement over >= 20 trailing reps  -> may auto-act, still logged
      ^  |
  earn |  | one disagreement demotes, window restarts
      |  v
  GATED       every action to a human      <- all classes start here
```

The ladder is the product's spine. A class starts gated, earns its way up on a boring, computed record, may be demoted in an instant, and, for the three classes that matter most, can never leave the ground floor. An engineer can test every rung: no sequence shorter than 20 reps graduates, any post-graduation disagreement demotes, a class-definition edit resets the count, and the never-graduate classes cannot be flipped by any call. Those are the gate-invariant tests, and they run in the build.

---

## 6. Gamification as incentive governance

The adoption layer is a scoring system, and every scoring system inside a workplace is a governance system whether or not it admits it. We treat it as one. The design goal is not to rank people. It is to reward the behavior a company needs (people using AI in the open) while protecting people from the failure modes that scoring systems always have. In the reference implementation this exists today only as a single running tally over one operator's own output `[ BUILT ]`; the per-person and per-organization version is a genuine rebuild, `[ PILOT-SCOPE ]`, and it is deliberately blocked on the mechanics specification owned by an originating member so it is designed once rather than twice.

**Mechanics.** Points are earned as rarity times impact, surfaced in a small number of tiers, with routine events silenced so the layer never becomes a notification feed. Streaks reward consistency. Leagues group people so that no one competes against a structurally different role. On top sit the rewards a company chooses to attach: time bought back, recognition, a points economy. The core value proposition to the individual is direct: the system rewards people who adopt AI, instead of leaving them afraid of being replaced by it. An employee who does far more in far less time buys time back, rather than being handed more work.

**Abuse cases, named first.** A scoring system attracts gaming, and we design against specific attacks rather than a vague ideal of fairness: inflating a metric by burning tokens without producing output; a coordinated or automated actor farming a time-weighted leaderboard (a real failure one contributor lived on a past project); outliers that look like excellence and are actually exploits; and the structural unfairness of penalizing meeting-heavy or non-technical roles for producing fewer of the measured events.

**Fairness countermetrics.** Against those: daily attainment caps, with the standing rule that about 90 percent of people never reach the cap, so the ones who do are the population to analyze, not celebrate. Outlier detection on the shape of scoring, not just its size. Consistency gating so a single burst cannot buy a league. Role-adjusted scoring so a role is measured against its own kind of work. These are aimed at protecting people from the system, which is the opposite of the usual purpose of workplace scoring.

**Visibility, appeal, and consent.** An individual sees their own data. Organization administrators see aggregate standings, without named-individual drill-down, unless the individual consents. Every scored item can be disputed through an appeal path, generalized from the reference implementation's own reject-to-learn correction loop, where a bad scoring event is flagged and the system stops repeating it. Participation is opt-in under a reviewed consent text before any collection begins; opting out stops forward scoring.

**Management limits.** The hardest limit is structural: there is no data path from scores to compensation systems, enforced at the code level, not by policy. The scoring store is its own access role, siloed from everything else (section 7). The system measures loop deletion and output, not hours and not presence; it is not built to watch people, and it is architecturally prevented from feeding the systems that would.

**The regulatory read, stated plainly.** Objective-weighted scoring plus gamification of workers reads, under the EU AI Act, as an Annex III high-risk system (worker monitoring and task allocation), enforceable from August 2026 (VENDOR/press). This is not an edge case for us; it is two of our pillars read literally. It is not a blocker for a US pilot, and it becomes binding the moment a client has an EU workforce. The useful consequence: the logging, human-oversight, and risk documentation the Act demands are the same artifacts the gate service and audit log already produce, so we keep them export-ready rather than bolt them on later.

---

## 7. Data posture

This is the first question a design partner's security team asks, so it gets a real answer rather than a reassurance. Everything below is `[ PILOT-SCOPE ]` as product machinery; the postures marked as proposed defaults carry a founder review gate and are tagged `[unverified]` until confirmed.

**Siloing.** Data classes do not share stores, keys, or access roles across sensitivity boundaries. In particular, scoring data and meeting capture never share a store, a key, or an access role with each other. The scoring store is the single most sensitive class and is held alone. This is control one of the aligned control set, not an afterthought.

**Tenant boundary.** For the pilot, a design partner's data lives in its own database instance under its own keys, physically segregated from the reference implementation and from any other account from day one. At n=1 this is cheaper to reason about and to attest than row-level security, and a partner's security team can audit it in a single meeting. The multi-tenant version adds schema-per-tenant separation with row-level security as the backstop, per-tenant keys, and a cross-tenant leak test that fails the build if a query ever crosses the line.

**Provenance.** Every event carries its initiator, approver, executor, tenant, timestamps, and a hash of the payload. The system shows where a fact came from and how fresh it is, and it narrates only the data path it actually used. Provenance is not a report that is generated later; it is the shape of every event as it is written.

**Retention (proposed defaults, founder gate, `[unverified]`).** Raw transcripts: 90 days, then auto-deleted unless the partner explicitly archives them. Derived artifacts (decisions, actions, commitments): the life of the engagement plus a contracted wind-down. Scoring events: the life of the engagement, then anonymized aggregates. The audit log: never deleted within the engagement, and exported to the partner at wind-down. Provider traffic: zero-retention requested in writing, with the one model-family carve-out that does not offer it kept off any sensitive path so the assumption never breaks silently.

**Consent and the hard walls.** Sanctioned capture only. The undisclosed-notetaker eviction in section 1 is the lesson encoded as policy: no undisclosed bots, ever. An executive designates the capture scope and all participants are disclosed to. Speaker attribution deploys only with explicit all-party consent, given the active wiretap and biometric litigation against that whole feature class (VENDOR/press, 2025 to 2026). Legal, board, and merger-related meetings are walled out of capture by policy before any regulated-client pilot, because a 2026 holding that AI conversations are not privileged makes that exposure concrete rather than theoretical (VENDOR/press).

**No pooled client-data learning.** This is the load-bearing commitment and the differentiator, so it is stated without hedging: no client's data is used to train models, and nothing learned inside one tenant pools into another. What compounds is client-specific. Each engagement's own configuration and its own evaluation sets make that engagement's system better over time, and they stay inside that engagement's boundary. The compounding asset is the fit of the system to one company, earned on that company's ground, never a shared pool skimmed across clients.

**What we hold, and what we do not.** We adopt the aligned control set now (a current data map, SSO and role-based access, tenant-scoped logging, encryption at rest and in transit, quarterly vendor review). We do not hold a SOC 2 Type II report, and we do not imply one. A formal audit is a 9-to-15-month effort triggered by the first real enterprise deal (SURVEY, compliance-market sources), and until it exists the engagement sells on relationship, demonstration, and this documented posture, not on a certificate we do not have.

---

## 8. What we deliberately do not claim

A trust document is defined as much by its refusals as by its claims. These are ours, stated so they cannot be read as hedging.

- **We do not claim immunity from the frontier labs.** A lab could build this capability. That is the market premise, not a fear we hide. The defensible part is adoption psychology, governance, and trusted delivery, earned per organization.
- **We do not claim the system runs your company.** The system orchestrates and proposes; a human holds the gate. Money, irreversible, and external actions never graduate to unattended action. Autonomy is earned per class and revocable in an instant.
- **We do not claim zero hallucination or perfect accuracy.** We claim provenance, traceability, and refusal outside authority. The system marks what it inferred versus what it observed, and exposes uncertainty rather than smoothing it.
- **We do not claim effortless integration.** Legacy integration is real friction. The consultative companion is the bridge across it, not a promise that the bridge is not needed.
- **We do not claim a throughput multiplier as a customer outcome.** An internal engineering benchmark exists and is being formalized with a methodology memo; no throughput figure appears in this document, and no such number is ever a customer promise.
- **We do not claim compliance we do not hold.** There is no SOC 2 report today. The controls are aligned; the certificate is a future event tied to a real deal.
- **We do not present the reference implementation as an installed customer.** It is a reference implementation operated by the founder. Its counts prove a pattern, not demand.
- **We do not present the research corpus or the skill registry as traction.** They are inputs and pattern-proof. Demand is measured by signed pilots, of which the honest count is stated wherever the question is asked.
- **We do not claim a name.** The product is intentionally unnamed until the position is locked and a mark clears legal review. The brackets are the design.

The through-line: trust is made visible as product behavior, not asserted as brand language. A system that cites its sources, distinguishes observation from inference, exposes its uncertainty, and refuses to act outside its authority earns more conviction than a product that merely appears finished. We are building for the first of those.

---

## Appendix: N=1 operating evidence

These are counts from the reference implementation, read from live telemetry. They are one operator's operating evidence, `N=1`. They demonstrate that the observe-and-propose pattern runs in production. They are not customer traction, and none should be read as adoption by anyone other than the founder.

| Signal | Value | Tag |
|---|---|---|
| Internal agent operation, running org-wide since | 2026-07-01 | MEASURED |
| Objective-alignment scoring, first run | 99.3 percent of commits mapped to the objective tree (275 of 277) | MEASURED |
| Recognition engine, live since | 2026-04-19; 5,027 points; a 23-day streak unbroken | MEASURED |
| Operator console (most-active repo) | 322 commits; session recall cut from 8 to 10 seconds down to 0.06 | MEASURED |
| Capture pipeline | 343 processed notes; roughly 47,000 embeddings; 5 real tasks auto-extracted from one meeting | MEASURED |
| Skill registry (an input, not traction) | 296 skills with a nightly self-improver | MEASURED |
| Consultative delivery engine | 6-plus active engagements, one at 25,000 dollars per month | MEASURED |

---

*Provenance. This document is a working technical specification for an unnamed product, authored 2026-07-09 from the foundation repository's architecture, data-governance, and product-law artifacts and the conversation-sweep dossiers behind them. Build-status and evidence tags are load-bearing; treat any untagged number as a defect. Founder: Jarred Winn (jarred@winn.solutions). No em dashes by house rule and recipient preference.*
