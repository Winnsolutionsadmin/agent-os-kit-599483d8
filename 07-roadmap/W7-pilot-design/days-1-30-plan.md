# Pilot days 1-30 plan: capture + ONE gated workflow (task 7.1)

**Workstream:** W7 pilot design + instrumentation | **Task:** 7.1 | **Authored:** 2026-07-08
**Status:** done, research-loop output. Threshold numbers inherit their [unverified] tags from `07-roadmap/W8-unit-economics/buyer-roi-model.md`; the structure is the deliverable, the numbers are candidates until the design partner signs the baseline.
**Inputs:** `01-overview/product-concept-overview-2026-07-08.md` sections 3, 5, 12 (pilot phasing counsel-kept 4/4), `07-roadmap/W8-unit-economics/buyer-roi-model.md` (day-30 thresholds), `icp-definition-v1.md` (buyer, disqualifiers 3-4, 6), decision 0003 (domino-1 = C-level chief of staff / organizer), `07-roadmap/W7-pilot-design/tasks.md`.
**Lineage legend:** MEASURED / SURVEY / VENDOR / [unverified], as defined in the ICP doc.

**Product law, stated up front because it governs this entire phase (counsel: "don't touch it"):**

1. ZERO ungated money, irreversible, or external actions. Every execution of the gated workflow passes a human gate. The zero is a hard requirement of the day-30 gate, not a candidate number.
2. Autonomy is earned via graduation only: 90% agreement with the executive's actual choice over 20+ reps per decision class. Graduation is NOT promised inside days 1-30; the first 30 days accumulate reps and evidence, nothing more.
3. Fail open to surfacing: decisions, money, deadlines, and irreversible items are never suppressed by the triage layer.
4. Capture is sanctioned and disclosed; no undisclosed capture in any context (must-have 7, the Winn.ai eviction lesson).

---

## 1. Shape of the phase

Counsel-kept pilot phasing (section 12, kept unanimously): **capture + ONE gated workflow, days 1-30.** Nothing else enters. Gamification waits for the day-30 evidence gate (see `days-31-90-plan.md`). The buyer is the CEO personally (ICP section 1); the seat is the chief-of-staff / organizer wedge, domino 1 (decision 0003).

Two deliberate constraints:

- **One workflow, not several.** The Stanford 51-deployment SURVEY (via the ICP doc) found 73% of successful deployments started deliberately small. One workflow also concentrates reps into one or two decision classes, which is the only way the 20+ reps graduation math can even begin inside 90 days.
- **Capture before automation.** Capture produces the artifacts (decisions, actions, commitments) that the gated workflow operates on and that the instrumentation (task 7.3) measures. No capture, no baseline delta, no honest math.

## 2. Candidate gated-workflow classes

All five candidates are drawn from what the fleet-of-one estate demonstrably runs today (overview section 3, Tier A unless noted). THE one workflow is selected with the design partner in week 1 using the rubric in section 3.

| # | Class | What the gated loop is | Estate evidence | Gate point | Decision class(es) |
|---|-------|------------------------|-----------------|-----------|---------------------|
| C1 | **Meeting pipeline: meeting to decisions/actions to task backbone** | Every designated meeting is captured; the agent proposes decision and action artifacts; the executive approves/edits/rejects; approved actions land in the task backbone | MEASURED: fieldy-clawdia pipeline (343 processed notes, 47k embeddings) + fieldy-to-ClickUp extraction armed in shadow mode (5 real tasks from one meeting); called the "biggest deferred ROI lever" (overview feature 15) | Approve/edit/reject card before any task is created or assigned | Task creation; task assignment |
| C2 | **Follow-up chase: commitment tracking + drafted chase messages** | Open commitments (own and others') tracked from capture + CRM; the agent drafts the chase message; the executive approves before ANY external send (external = always gated, product law, no graduation exception for external sends without a separate founder-level decision) | MEASURED: CRM decay scoring + auto-reach-out drafts on the reference implementation; the addressed pain was "39 overdue follow-ups, 3-6 hours/week" (n=1; generalization [unverified]) | Approve/edit/reject before send; send itself is the external action | Chase-draft approval; recipient/timing selection |
| C3 | **OKR readout: weekly alignment readout to the executive** | Work activity scored against the org's objective tree; the agent assembles the weekly readout; the executive approves before it circulates beyond their own desk | MEASURED: the-sage `score_alignment()` (99.3% first-run on 275/277 commits) but the outcome-movement axis is a self-flagged gap and client-side data sources are unproven [unverified as a client workflow] | Approve before circulation (circulation = external/reputational action) | Readout accuracy sign-off |
| C4 | **Recognition events: achievement engine on the executive's own operating loop** | Points/tiers/streaks scored against real events (meetings held, follow-ups cleared, decisions closed); day 1-30 scope is the EXECUTIVE ONLY, single tally, no employee scoring | MEASURED: mini achievement engine live since 2026-04-19 (5027 points, 23-day streak, ~25-event catalog); today's model is one tally, per-person model is a named gap | Catalog approval + any visible-to-others event gated | Event-catalog fit |
| C5 | **Pre-meeting briefing pack** | One hour before each designated meeting, the agent assembles a briefing (people context, open commitments, last-meeting deltas); executive consumes, corrects, rates | MEASURED: Lobster pre-meeting briefings (7 sections, 1 hour ahead) + person-context 360 on the reference implementation | Read-only output; the gate is correction/rating (lowest-risk class; no money/irreversible/external surface at all) | Briefing accuracy |

Note on C4: the achievement engine at days 1-30 is instrumentation and demonstration, not gamification of the partner's employees. Employee-facing gamification enters only at day 31+ against the evidence gate, opt-in, with anti-abuse on (see `days-31-90-plan.md`). Choosing C4 as THE gated workflow does not move gamification earlier.

## 3. Selection rubric: picking THE one workflow in week 1

Run in the week-1 discovery session with the CEO. Score each candidate 1-5 per criterion; weights in parentheses. The rubric output is an internal prioritization tool and never appears on a slide or in the partner-facing plan (CLAUDE.md hard law analogue for readiness scores).

| Criterion | Weight | What it asks |
|-----------|--------|--------------|
| R1. Pain match | 3 | Does this workflow attack the buyer's own stated top loop (from the B1 time audit categories: meeting notes, follow-up chasing, status assembly, reporting prep)? The baseline instrument tells us; do not guess. |
| R2. Rep frequency | 3 | Will it generate 15+ gated executions inside 30 days (the day-30 candidate threshold) and plausibly 20+ reps per decision class inside 90 days (the graduation floor)? Daily-cadence loops beat weekly ones. |
| R3. Measurability | 2 | Does it move B1 (hours) or B2 (follow-up debt), the contracted metric pair from `buyer-roi-model.md`, with a clean before/after? |
| R4. Gate cleanliness | 2 | Is there one obvious human-gate point that catches every money/irreversible/external surface? Ambiguous gate topology disqualifies. |
| R5. Estate evidence strength | 2 | Tier A shipping (5) down to designed-only (1), per overview section 3. We deploy what already runs; the pilot is not a build project. |
| R6. Blast radius if wrong | 2 | Reversibility of a bad approved output. Client-experience degradation risk is a hard disqualifier at any score (delivery law 19). |
| R7. Story value | 1 | Does the day-90 artifact demonstrate the trusted-companion category (decision 0003) to a known investor verifying the ledger entry? |

Pre-discovery expectation, stated for honesty and falsifiable in week 1: C1 (meeting pipeline) and C2 (follow-up chase) score highest on estate evidence and metric fit, and C2 maps directly onto the MEASURED B2 analogue. But R1 belongs to the buyer's own baseline data; the rubric decides, not this prediction. [unverified until the week-1 session happens]

Selection is made WITH the design partner, in the room, and recorded as a ledger-worthy decision artifact (workflow chosen, rubric scores, executive's stated reason).

## 4. Pre-day-1 (contract-mandated, from the ICP disqualifiers and buyer ROI model)

These exist before the clock starts; a partner who refuses them is disqualified (ICP disqualifier 4):

1. **B1 baseline:** 2-week executive time audit on capturable loops (instrument defined in `instrumentation-spec.md`).
2. **B2 baseline:** day-0 open follow-up-debt count (CRM/task export + meeting-note sweep).
3. **B4 baseline:** timestamp audit of the chosen workflow's last 90 days (runs immediately after week-1 selection; the only baseline that waits for selection).
4. **Named business owner** signs the baseline; **written kill criterion** agreed; **dollarization rule** settled (buyer's own rate or raw hours; never an asserted market rate).
5. **Capture scope designation:** the executive designates the meeting surface; disclosure-sensitive scope is carved out until W9 lands (ICP disqualifier 6). Consent posture per `instrumentation-spec.md` section 5; W9 is a pre-pilot dependency for anything touching partner-employee data.

## 5. Week-by-week

**Week 1: discovery, selection, capture go-live.**
- Day 1-2: discovery session with the CEO; walk the B1 audit results; run the section-3 rubric; select THE workflow; record the decision artifact.
- Day 2-3: capture live on the designated meeting surface (sanctioned, disclosed, disclosure-sensitive scope carved out). Every captured meeting produces decision/action artifacts from day one.
- Day 4-5: gate surface stands up for the chosen workflow (approve/edit/reject decision cards; the estate pattern is the bar Approvals panel / command-center cards, overview features 2 and 21). B4 timestamp audit kicked off.
- Weekly CEO check-in cadence starts (the strongest SURVEY success predictor; it is also our kill-criterion early-warning line).

**Weeks 2-4: the gated workflow in production.**
- Every execution passes the gate; every gate decision logs an agreement/disagreement rep per decision class (graduation math accumulates from rep 1; see `instrumentation-spec.md`).
- Capture coverage tracked weekly against the 90%+ candidate threshold [unverified candidate, from `buyer-roi-model.md`].
- B2 follow-up-debt count re-measured weekly; day-30 gate wants direction, not magnitude.
- Any attempted ungated money/irreversible/external action is a sev-1 product-law event: workflow pauses, incident recorded, executive informed at the next check-in at latest.
- No scope additions. Requests for a second workflow are logged for the day-31+ plan and declined for this phase.

## 6. The day-30 gate (mirrors `buyer-roi-model.md` section 3; do not fork the numbers)

- Capture coverage 90%+ of the designated meeting surface [unverified candidate].
- The ONE gated workflow in production with 15+ gated executions [unverified candidate] and ZERO ungated money/irreversible/external actions (hard requirement).
- Baseline fully instrumented and signed (B1, B2, named owner).
- B2 trending down from day-0 count (direction, not magnitude).
- Kill-criterion checkpoint evaluated; if capture adoption is refused by the executive personally, the CEO-ownership predicate has failed (ICP disqualifier 1) and the pilot stops.
- Achievement ledger writes (per `buyer-roi-model.md` and W10 schema): day-30 gate cleared, capture-coverage %, gated-execution count with zero-ungated attestation, baseline artifact. The signed pilot itself was already recorded at signature and is THE raise trigger; these are supporting evidence.

Clearing this gate is the entry condition for gamification. Day 31 is the earliest calendar date, not an entitlement; the evidence bar governs (`days-31-90-plan.md` section 1).

## 7. Open items needing Jarred

1. Confirmation that all five candidate classes may be shown to the design partner, or whether any (C3's client-side data-source gap, C4's demonstration-only framing) should be held back from the week-1 menu.
2. Whether external sends (C2's chase messages) remain permanently gated regardless of graduation, or graduate like other decision classes. Product law says never auto-act on external actions without a human gate; this plan treats external sends as non-graduating until Jarred says otherwise. [needs founder confirmation]
3. The rubric weights in section 3 are authored here, not founder-set [unverified as founder preference].
