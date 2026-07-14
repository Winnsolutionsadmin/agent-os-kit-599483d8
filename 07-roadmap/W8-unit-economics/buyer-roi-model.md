# Buyer ROI model (task 8.3)

**Workstream:** W8 unit economics + ICP (counsel blind spot 1) | **Task:** 8.3 | **Authored:** 2026-07-08
**Status:** done, research-loop output. No founder gate on this task, but every threshold number below is a proposed candidate [unverified] until the design-partner discovery conversation and the W7 baseline instrument confirm them. Feeds 8.5 (one-page summary), W7 (pilot contract terms), W1 (deck; internal bands and readiness scores stay off slides per CLAUDE.md hard law).
**Inputs:** `icp-definition-v1.md` (8.1), `vendor-pricing-scan.md` (8.4), `pricing-model-options.md` (8.2, drafted), `01-overview/product-concept-overview-2026-07-08.md` sections 3, 7, 12, `03-execution/pilot-design.md` (general research only; account-specific passages invalid per CLAUDE.md correction 3), decision 0003.
**Lineage legend:** MEASURED / SURVEY / VENDOR / [unverified], as defined in the ICP doc.

**Two framing laws govern everything here:**

1. **The raise trigger is a SIGNED design-partner pilot** (founder decision, `07-roadmap/ROADMAP.md` resolved questions). The metrics below are supporting evidence in the achievement ledger, not the trigger. Nothing in this model gates the raise on a metric.
2. **Loop-deletion framing over raw multipliers** (CLAUDE.md hard law). The ROI story is "these loops stopped consuming the executive," not "Nx productivity."

---

## 1. Who the ROI accrues to

The domino-1 buyer is the CEO personally (ICP section 1). The pilot's unit of value is therefore the executive's own time, attention, and follow-through, not headcount cost. This matches the strongest SURVEY success predictor (CEO personal ownership with weekly check-ins; Stanford 51-deployment study via `03-execution/pilot-design.md`) and the adoption contract (reward-not-replace; disqualifier 2 in the ICP).

## 2. Candidate baseline metrics (instrument BEFORE day 1)

The pilot design already requires a pre-pilot timing baseline, a named business owner, and a written kill criterion before day 1 (`03-execution/pilot-design.md`; SURVEY support: named metric at kickoff and named C-1+ sponsor are two of the four factors explaining 71% of payback-speed variance, attributed to Bain, secondhand). Candidate metrics, ranked by evidence strength:

| # | Metric | Baseline instrument | Internal evidence | Lineage |
|---|--------|--------------------|-------------------|---------|
| B1 | **Executive hours per week on capturable loops** (meeting notes, follow-up chasing, status assembly, reporting prep) | 2-week time audit pre-pilot | 3-6 hours/week recovered for one operator on the reference implementation | MEASURED (reference implementation, n=1; generalization [unverified]) |
| B2 | **Open follow-up debt** (commitments made in meetings that are overdue) | CRM/task export + meeting-note sweep at day 0 | 39 overdue follow-ups surfaced and cleared on the reference implementation | MEASURED (reference implementation, n=1) |
| B3 | **Executive attention cost per day of delegated work** (touches + approvals + time) | measured in-product from day 1; pre-pilot proxy is B1 | demo after-state: 14 actions, 3 approvals, 41 seconds of attention for a day of agent work | MEASURED as a built demo scenario, NOT a client result (must be labeled as such everywhere) |
| B4 | **Decision latency on the one gated workflow** (request-to-decision elapsed time) | timestamp audit of the chosen workflow's last 90 days | none yet; instrument exists in W7 task 7.3 scope | [unverified] as to expected magnitude |
| B5 | **Meeting-output conversion** (share of meetings producing captured decisions/actions vs evaporating) | meeting-count vs captured-artifact count, first 2 weeks | reference implementation captures by default; client rate unknown | [unverified] |

Primary metric recommendation: **B1 (hours) + B2 (follow-up debt)** as the contracted pair, because both have MEASURED internal analogues and both are auditable by the buyer's own records. B3 is the demo talk-track and becomes a client MEASURED number during the pilot. B4/B5 are secondary instrumentation.

Dollarization rule (honest math): hours are dollarized ONLY at the buyer's own stated rate for their time, agreed at kickoff, never at an asserted market rate. If the buyer declines to dollarize, report hours raw.

## 3. 30/60/90 success thresholds (tied to the counsel-kept pilot phasing)

Pilot phasing is counsel-kept unanimously: capture + one gated workflow days 1-30, gamification 31-90 (`01-overview` section 12). Every threshold number is a candidate [unverified] until the design partner signs the baseline; the STRUCTURE (what is measured at each gate) is the deliverable here.

### Day 30: capture live + one gated workflow in production

- Capture coverage: 90%+ of the executive's designated meeting surface captured and producing action/decision artifacts [unverified candidate; "designated" excludes any disclosure-sensitive scope carved out per ICP disqualifier 6 until W9 lands].
- The one gated workflow is in production with 15+ gated executions, ZERO ungated money/irreversible/external actions (product law; the zero is a hard requirement, not a candidate).
- Baseline fully instrumented: B1 time audit and B2 follow-up-debt count signed by the named business owner.
- Early signal: B2 follow-up debt trending down from the day-0 count (direction, not magnitude, at this gate).
- **Kill criterion checkpoint:** the written kill criterion is evaluated; if capture adoption is refused by the executive personally, the CEO-ownership predicate has failed (ICP disqualifier 1) and the pilot stops.
- **Achievement ledger records:** signed pilot (already recorded at signature; THE raise trigger), day-30 gate cleared, capture-coverage %, gated-execution count with zero-ungated attestation, baseline artifact.

### Day 60: gamification live + adoption

- Gamification layer live for the pilot cohort with anti-abuse mechanics on from day one (counsel-kept; Nick Metzler's mechanics definition due 7/31 shapes the specifics).
- Adoption: 60%+ weekly active participation of the designated pilot cohort [unverified candidate].
- B1: executive hours recovered at or above 3 hours/week, the bottom of the MEASURED reference band [unverified as a client expectation; the band itself is MEASURED n=1].
- B2: follow-up debt reduced 50%+ from day-0 count [unverified candidate].
- Graduation progress: at least one decision class accumulating reps toward the 90%-agreement-over-20+-reps graduation bar (product law; graduation itself is NOT promised by day 60).
- **Achievement ledger records:** day-60 gate cleared, adoption %, hours-recovered vs baseline, follow-up-debt delta, decision-class rep counts.

### Day 90: ROI evidence + conversion decision

- B1 sustained: hours recovered holding at 3-6 hours/week across 4+ consecutive weeks (MEASURED band, n=1, applied as candidate).
- B2: follow-up debt at or near zero and staying there (the reference implementation's end state, MEASURED n=1).
- B3 becomes a client MEASURED number: attention cost per delegated-work day reported from in-product telemetry.
- At least one decision class at or past graduation (90% agreement, 20+ reps) OR a documented reason it is not yet appropriate (honest math beats a vanity graduation).
- Business outcome: the buyer converts to the post-pilot retainer (8.2 Option A conversion, $20-30K/mo band anchored on the MEASURED $25K/mo precedent), agrees to referenceability, and opens the domino-2 sponsorship conversation.
- **Achievement ledger records:** day-90 gate cleared, sustained-hours evidence, follow-up-debt end state, graduation status per decision class, conversion signed (or not, with reasons), reference permission, domino-2 conversation opened (yes/no).

ROI arithmetic at day 90, buyer's view (illustrative, honest-math form): pilot fee in the $45-60K working band ([unverified], 8.2) against (a) 3-6 hours/week of CEO time recovered, dollarized only at the buyer's own rate, (b) follow-up debt cleared, (c) a production-grade gated workflow they keep, and (d) the same-budget-line comparison: a full-time chief of staff costs $240-265K+/yr true cost and a fractional one $7-14K/mo (VENDOR secondhand, via 8.4). The pilot must NOT be sold on a payback multiple; it is sold on deleted loops plus the head start (trusted-companion positioning, decision 0003).

## 4. Expansion math: domino-2, the engineer tier

Founder-confirmed sequence (decision 0003): engineers next, revamp/overhaul. The domino-2 sale is an internal referral by the domino-1 CEO after 90 days of gated agent work on their own calendar (ICP section 5).

- **Offer shape:** engineering-department overhaul informed by Carter Razink's Recurro framework (his framework, an input to the engineering pillar, not the product; CLAUDE.md correction 2). Offer definition sharpens when Carter's Recurro doc (due 7/10) and methodology memo (due 7/15) land.
- **Evidence discipline:** the 16x case study (4-engineer team at 16x baseline vs an 18-engineer control at 2.5x) is [unverified] until Carter's methodology memo lands. Until then, the only usable framing is output-parity: "4 matched the output of 18" (CLAUDE.md hard law; `01-overview` section 12, revision 8). The domino-2 ROI story is therefore output-parity + loop-deletion, never a multiplier.
- **Buyer and budget line:** CTO/VP Engineering, engineering productivity/tooling budget (ICP section 5). VENDOR (secondhand) precedent that engineering buyers accept outcome-shaped pricing: Cognition/Devin outcome pricing at $492M ARR run-rate (`04-competitive/landscape-consulting-hybrids.md`).
- **Baseline metrics for domino-2** (candidates, all [unverified] until Recurro doc lands): throughput per engineer-week on the buyer's own definition (PRs/features/tickets), cycle time, and cost-per-shipped-unit; instrumented the same way as domino-1 (pre-engagement baseline, named owner, kill criterion).
- **Entry condition:** domino-1 must clear its day-90 gate first. Domino-2 pull is supporting ledger evidence for the raise narrative, not the trigger (ROADMAP resolved questions).
- **Account expansion shape (illustrative, [unverified]):** domino-1 retainer ($20-30K/mo band) + a domino-2 overhaul engagement (boutique-transformation comparables $50-300K, VENDOR secondhand via 8.4) + eventual domino-3 whole-org software (enterprise-assistant ACV comparables $200-600K/yr at mid-market headcounts, VENDOR secondhand via 8.4). No account-level LTV number is asserted; the shape is the claim, the numbers arrive with signed engagements.
- **Account-shape requirement carried from ICP:** an engineering org big enough for a before/after story, plausibly 10+ engineers [unverified inference].

## 5. What the achievement ledger tells investors

The funding model is achievement + faith from investors Jarred already knows (decision 0003). The ledger sequence this model produces:

1. **Signature (the trigger):** a signed 90-day design-partner pilot with a named CEO owner, a written baseline, and a kill criterion. This alone authorizes the raise conversation.
2. **Day 30:** capture live, one gated workflow in production, zero ungated actions, baseline signed.
3. **Day 60:** gamification live with anti-abuse on, adoption threshold met, hours-recovered signal.
4. **Day 90:** sustained hours evidence, follow-up debt cleared, graduation status, conversion to retainer, reference permission, domino-2 conversation.
5. **Beyond:** domino-2 engagement signed inside the same account = the expansion motion demonstrated once, which is the whole GTM ladder in miniature.

Each entry is a fact a known investor can verify by talking to the design partner. None of it requires a multiplier claim, and none of it puts a readiness score or internal band on a slide.

## 6. Open items needing Jarred or a source

1. All threshold numbers in section 3 (90% capture coverage, 15+ gated executions, 60% adoption, 50% follow-up-debt reduction, 3-6 hours applied as client expectation) are [unverified] candidates for the design-partner negotiation.
2. B1/B2 generalization from the n=1 reference implementation to target buyers is [unverified] until discovery (already flagged in ICP section 1).
3. The B3 demo figure (14 actions, 3 approvals, 41 seconds) must always carry its "built demo scenario, not a client result" label; confirm Jarred wants it in the pilot contract talk-track at all.
4. Domino-2 baseline metrics await Carter's Recurro doc (7/10) and methodology memo (7/15); the 16x claim stays [unverified] with output-parity fallback until the memo lands.
5. The dollarization rule (buyer's own rate or raw hours) as pilot-contract language: founder sign-off belongs with the W7 contract terms.
