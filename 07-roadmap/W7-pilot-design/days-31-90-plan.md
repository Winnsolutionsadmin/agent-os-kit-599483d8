# Pilot days 31-90 plan: gamification entry, W4 handshake, opt-in posture (task 7.2)

**Workstream:** W7 pilot design + instrumentation | **Task:** 7.2 | **Authored:** 2026-07-08
**Status:** done, research-loop output. Threshold numbers inherit [unverified] tags from `07-roadmap/W8-unit-economics/buyer-roi-model.md`. The gamification specifics in this phase are shaped by Nick Metzler's mechanics definition (due 7/31, W4); this plan defines the entry gate, the handshake, and the posture, not the mechanics themselves.
**Inputs:** `days-1-30-plan.md` (7.1), `buyer-roi-model.md` (day-60/90 thresholds), `01-overview/product-concept-overview-2026-07-08.md` sections 5 and 12 (counsel-kept: gamification decoupled from comp + anti-abuse day one), `07-roadmap/W4-gamification/tasks.md`, ICP disqualifier 2 (replace-not-reward), decision 0003.
**Lineage legend:** MEASURED / SURVEY / VENDOR / [unverified], as defined in the ICP doc.

**Product law continues unchanged through days 31-90:** zero ungated money/irreversible/external actions; graduation only via 90% agreement over 20+ reps per decision class; graduation is a per-decision-class earned status, never a phase entitlement. Gamification adds NO new autonomy anywhere.

---

## 1. Entry criteria: gated on day-30 EVIDENCE, not the calendar

Day 31 is the earliest possible calendar date for the gamification layer. It is not automatic. Gamification enters only when the day-30 evidence gate from `days-1-30-plan.md` section 6 has cleared in full:

1. Capture coverage 90%+ of the designated meeting surface [unverified candidate].
2. The one gated workflow in production with 15+ gated executions [unverified candidate] and ZERO ungated money/irreversible/external actions (hard requirement; a single ungated action means the gate is not cleared, regardless of everything else).
3. Baseline signed (B1 time audit + B2 follow-up-debt count, named business owner).
4. B2 trending down from day 0 (direction, not magnitude).
5. Kill-criterion checkpoint passed; CEO personally engaged (weekly check-ins held).

**If the gate has not cleared by day 30, phase 1 continues until it does.** The pilot calendar slips; the evidence bar does not. This is the honest-math posture applied to phasing: a gamification layer launched on top of weak capture data scores vanity, and a real outcome-data source is a precondition for any score being more than a vanity metric (must-have 17).

Two additional entry conditions specific to the gamification layer itself:

6. **Anti-abuse mechanics exist and are switched on at launch** (counsel kept unanimously: anti-abuse from day one, meaning day one OF GAMIFICATION, which is day 31 at the earliest). No anti-abuse spec, no launch. See the W4 handshake below.
7. **The opt-in cohort exists:** at least the executive plus a designated pilot cohort who have individually opted in (section 3). Consent posture per `instrumentation-spec.md` section 5; W9 governance is a pre-pilot dependency for partner-employee data, so the cohort mechanism must already have cleared that bar before day 31.

## 2. W4 handshake: what W7 needs from Nick's 7/31 mechanics definition

Nick Metzler (originating member; game design, adoption mechanics, anti-abuse author of record) owes the gamification mechanics definition 7/31 (CLAUDE.md live commitments; W4 task 4.1). W4 task 4.4 (pilot-phase gamification plan) is explicitly blocked on W7.2, this document; this section is W7's side of the handshake. All outreach to Nick about scope goes through Jarred (W4 human gates).

What the pilot needs from the mechanics definition, in priority order:

| # | Needed from W4/Nick | Why the pilot needs it | Pilot deadline pressure |
|---|--------------------|------------------------|-------------------------|
| H1 | **Minimum viable mechanic set for a small cohort** (points/tiers/streaks shape that works at pilot scale, not org scale) | The estate's achievement engine is MEASURED but single-tally; the per-person/per-team model is a named gap (overview feature 9). The pilot cohort is small; leagues designed for hundreds may not degrade gracefully to 5-15 people | Needed before the partner's day-31 (earliest); 7/31 delivery means any pilot signing before ~7/25 needs an interim answer from Nick via Jarred |
| H2 | **Anti-abuse spec sized to pilot scale:** caps, outlier detection, role-adjusted scoring, minimum-consistency gating (Nick's 6/30 design raw material: daily attainment caps, "90% never hit the cap, analyze the ones that do", fake-outlier detection) | Entry condition 6 above; anti-abuse on from day 31 is counsel-kept and non-negotiable | Same as H1; anti-abuse gates the launch |
| H3 | **Event-catalog mapping:** which instrumented events (from `instrumentation-spec.md` section 2) score, at what rarity/impact | The scoring engine consumes the same event stream as the ROI instrumentation; one stream, two consumers. Nick defines scoring semantics; W7 defines the events | Before day 31 |
| H4 | **Comp-decoupling boundary language** for the cohort-facing explanation (what points can and cannot ever affect) | Section 4; the pilot needs partner-facing words, not just an internal rule | Before cohort opt-in conversations |
| H5 | **The role-adjustment model for a mixed cohort** (executive + assistants + ops roles score differently) | Must-have 15 (role adjustment) applied to a real, small, role-diverse cohort | Before day 31, degradable: launch executive-plus-volunteers first if role model is late [unverified as acceptable; founder call] |

What W7 gives W4 back: the day-30 evidence package (real capture coverage, real event volumes, real decision-class rep counts) so Nick's mechanics tune against MEASURED pilot data instead of assumptions, and the entry-criteria structure above so W4.4 can be written against a fixed gate.

## 3. Opt-in posture

- **Individual opt-in, never enrollment by decree.** Each cohort member opts in personally, in writing, and can opt out at any time without stated reason. Opt-out deletes them from scoring surfaces going forward; retention/deletion mechanics for already-collected scoring data follow the W9 posture (W9 task 9.3; scoring data is named there as the sensitive class).
- **Reward-not-replace is the adoption contract** (must-have 18; ICP disqualifier 2). The layer exists so the partner can reward and retain people. A partner who wants scoring as a performance-management or headcount instrument during the pilot is violating the contract; that is a kill-criterion-grade conversation with the CEO.
- **The executive goes first.** The CEO is scored from day 31 on their own operating loop (the day 1-30 achievement instrumentation makes this continuous). Leaders being visibly measured before their people is the felt-fairness precondition [unverified as sourced doctrine; design stance for founder confirmation].
- **Visibility is cohort-controlled:** individual scores visible to the individual; comparative surfaces (leaderboards, leagues) only among opted-in members; no management-facing individual score reporting during the pilot. Aggregate adoption and outcome metrics (the 8.3 thresholds) are what the CEO sees. [unverified as final posture; W9 task 9.3 founder review owns the values statement]

## 4. Comp-decoupling, stated plainly

**Scores, points, tiers, streaks, and leagues are decoupled from compensation. Nothing in the gamification layer feeds salary, bonus eligibility, promotion, or termination decisions during the pilot.** This is counsel-kept unanimously (W4 task 4.3; overview section 12 kept list) and is stated in the pilot terms, in the cohort opt-in document, and in the first cohort briefing.

Rewards that ARE in scope: recognition, opt-in perk-shaped rewards of the kind in the estate's design raw material (half-days off, cosmetics, opt-in bonus pools as a partner-funded choice per must-have 18's $250k-pool example). Any partner-funded reward pool is the partner's own comp decision made outside the scoring system, papered by them; the scores never make the decision. [Reward specifics await Nick's mechanics and partner appetite; unverified]

## 5. Days 31-60: gamification live + adoption

- Gamification live for the opted-in cohort with anti-abuse on from launch day (entry conditions 6-7).
- The one gated workflow continues uninterrupted; decision-class reps keep accumulating toward graduation. Gamification changes nothing about gates.
- Capture surface may widen within the designated scope if the CEO asks, but no second gated workflow enters before day 60, and then only if the first workflow's rep accumulation will not be starved [unverified as policy; founder call at the day-60 check-in].
- Weekly CEO check-ins continue; weekly adoption and anti-abuse review added (who is hitting caps, outlier flags; Nick's "analyze the ones that do" rule applied).

**Day-60 gate (mirrors `buyer-roi-model.md` section 3; do not fork the numbers):**
- Gamification live with anti-abuse on (attested).
- Adoption: 60%+ weekly active participation of the designated pilot cohort [unverified candidate].
- B1: executive hours recovered at or above 3 hours/week, the bottom of the MEASURED n=1 reference band [unverified as client expectation].
- B2: follow-up debt reduced 50%+ from day-0 count [unverified candidate].
- Graduation progress: at least one decision class accumulating reps toward the 90%/20+ bar (graduation itself NOT promised by day 60).
- Achievement ledger writes: day-60 gate cleared, adoption %, hours-recovered vs baseline, follow-up-debt delta, decision-class rep counts.

## 6. Days 61-90: sustain, graduate honestly, convert

- Sustain the metric pair: B1 holding at 3-6 hours/week across 4+ consecutive weeks (MEASURED band n=1, applied as candidate); B2 at or near zero and staying there.
- B3 becomes a client MEASURED number: executive attention cost per delegated-work day, reported from in-product telemetry (until then B3 is only the built demo scenario and is labeled as such everywhere).
- Graduation review per decision class: at or past 90% agreement over 20+ reps means the class MAY graduate to auto-act, with the executive's explicit sign-off per class, EXCEPT classes touching money, irreversible, or external actions, which do not graduate in the pilot (per `days-1-30-plan.md` open item 2, pending Jarred). A class not yet at the bar gets a documented reason; honest math beats a vanity graduation.
- Conversion conversation: post-pilot companion retainer ($20-30K/mo working band anchored on the MEASURED $25K/mo precedent; band [unverified], `pricing-model-options.md`), referenceability, and the domino-2 sponsorship conversation (engineers next, decision 0003; offer shaped by Carter Razink's Recurro framework docs, his framework, an input to the engineering pillar, not the product).

**Day-90 gate (mirrors `buyer-roi-model.md`):** sustained B1 evidence, B2 end state, B3 client-measured, graduation status per class (or documented reasons), conversion signed or not with reasons, reference permission, domino-2 conversation opened. All of it writes to the achievement ledger as supporting evidence; the raise trigger remains the SIGNED pilot, already recorded at signature (W10 task 10.2, founder-defined).

## 7. Open items needing Jarred or Nick (via Jarred)

1. H1-H5 handshake items from Nick's 7/31 mechanics definition; interim answers needed if the pilot signs before ~7/25.
2. The executive-goes-first visibility stance and the cohort-controlled visibility posture (section 3) [unverified; overlaps W9 task 9.3 founder review].
3. Whether a second gated workflow may enter at day 60+ (section 5) [founder call].
4. Whether the H5 degradation path (launch without the role-adjustment model, executive-plus-volunteers only) is acceptable if Nick's role model is late [founder call].
5. All threshold numbers remain [unverified] candidates until the design partner signs the baseline (inherited from 8.3).
