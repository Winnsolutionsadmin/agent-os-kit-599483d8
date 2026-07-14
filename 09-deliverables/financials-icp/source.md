# Financials and ICP: the unit-economics spine

*The load-bearing financial model for the launch kit. Other artifacts cite ITS numbers rather than inventing their own (counsel addendum, unit economics as spine). This document is the internal source of truth; the external-facing surface is the pilot P&L only.*

**Authored:** 2026-07-09 (recovery author) | **Built on:** the W8 unit-economics workstream (`07-roadmap/W8-unit-economics/`) and the W7 pilot design (`07-roadmap/W7-pilot-design/`). It distills and reconciles them; it does not duplicate them.
**Status:** spine assembled. Every dollar figure is either MEASURED (approved), VENDOR (a citable market comparable), or an internal ASSUMPTION / [unverified] working candidate that the founder must set. No unapproved band appears in any external artifact.

## Lineage legend

MEASURED = instrumented first-party or a signed engagement. SURVEY = a third-party study. VENDOR = a vendor-published or third-party-reported market figure. CORPUS = an internal build, self-reported, not independently benchmarked. ASSUMPTION = a stated design estimate held to its range. [unverified] = an internal working candidate awaiting founder confirmation.

## Governing laws (fixed, not options)

1. **Pilot P&L only.** External materials show a single-pilot P&L. There is no multi-year revenue hockey stick. The 24-month model in section 7 is an internal capacity-and-survival model (scenario planning on five levers), not a revenue projection, and it is labeled as such wherever it travels.
2. **Consulting revenue first; software margin is designed, not running.** The spine leads with consultative delivery economics. Software margin is a horizon shape, named in the future tense, never claimed as present.
3. **Forward-deployed service becoming software.** The delivery model is engineered so that each engagement encodes reusable playbook and product, the way Palantir treats forward-deployed work as product formation rather than one-off labor (VENDOR). The margin story is the trajectory of that conversion, not a mature-SaaS assumption.
4. **No mature-SaaS margin assumptions.** Every margin figure sits in the honest services-to-hybrid band (section 5). SaaS-grade gross margins are never assumed for this business at this stage.
5. **Full founder cost is always in the model.** Fully loaded founder delivery time is the largest cost line and the binding constraint. Single-operator capacity is a named counsel blind spot; the model treats it as real, not free.
6. **Price is anchored to the value of a chief of staff plus an engineering lift, never per-seat.** Per-seat SaaS pricing is the wrong shape for the domino-1 seat and appears only at the domino-3 whole-org software tier.
7. **No throughput multiplier anywhere.** The 16x is retired from all external use (counsel addendum 3 S1, R4). The engineering delivery-cost advantage is an internal benchmark, methodology memo pending, and is never a customer promise. No output-parity comparison, no 3x/10x band.
8. **Honest math and no em dashes.** Every number carries its basis. No client or partner is named; the fleet-of-one is a reference implementation, never an installed customer.

---

## 1. The ICP as firmographics (not the go-to-market motion)

The domino sequence (C-levels, then engineers, then everyone else) is a **go-to-market motion, not an ICP** (counsel blind spot 7). This section defines who the first buyer's *company* is, in firmographic terms a stranger could screen against.

| Firmographic | Domino-1 target | Basis |
|---|---|---|
| **Headcount / revenue band** | Mid-market: roughly $50M-$3B revenue, lean executive team | VENDOR/press: the lab and SI mid-market pushes (Accenture Edge + Google Cloud; the Anthropic + PE JV) target the $300M-$3B band; positioned below the large-enterprise tier the global SIs serve first. [unverified] as a founder decision. |
| **Vertical candidates** | Vertical-agnostic on product; screened for (a) a decision-bottlenecked executive and (b) an internal engineering org for domino-2. Candidate concentrations: digital-asset / fintech operators, PE-owned operating companies at an ownership-transition moment, founder-led growth-stage firms | Reasoned from the trigger conditions below + VENDOR/press PE-portfolio targeting. Verticalization is a later choice; v1 is a firmographic screen, not a named industry. |
| **Incumbent tools they already pay for** | Meeting capture (Otter, Fireflies, Fathom, Gong), an OKR platform (Lattice, 15Five, Betterworks), point AI assistants, and a human or fractional chief of staff. The engagement displaces none of them at domino-1; it sits above them and deletes the loops between them | VENDOR pricing scan. The incumbent stack is the noise floor the engagement is priced *against*, not with. |
| **Buyer titles** | Domino-1: the CEO personally (or a COO/President who fully owns operations). Domino-2: CTO or VP Engineering, with the CEO as internal sponsor. Domino-3: whole-org, pulled by demand | SURVEY: CEO personal ownership with weekly check-ins is the single strongest success predictor across 51 enterprise AI deployments (Stanford Digital Economy Lab, via pilot-design). |
| **The Monday-morning trigger condition** | The executive is personally the bottleneck: overflowing meeting load, follow-up debt that never clears, status and reporting assembly done by hand, and a board asking for an AI story. On a bad Monday they are the single point of failure for their own company's follow-through | MEASURED analogue (reference implementation, n=1, generalization [unverified]): 39 overdue follow-ups cleared, 3-6 hours/week recovered for one operator. |

**Disqualifiers (screen out fast).** The CEO will not personally own it; replace-not-reward intent (headcount reduction as the headline); demands day-1 autonomy on money/irreversible/external actions; will not sign a baseline and a kill criterion; procurement-led cold buying with no warm path; disclosure-sensitive capture scope before the data-governance posture (W9) exists; a live customer-facing crisis; and (soft) no engineering org, which caps the account at the chief-of-staff seat because domino-2 has nothing to land on.

**Why firmographics and not the motion:** the motion tells you the *order* you sell in; the firmographics tell an investor exactly which company to introduce. Both are needed; only the firmographics belong in the design-partner profile.

---

## 2. Buyer ROI model (explicit formulas; executive hours alone cannot carry it)

The ROI accrues to the executive's own operating capacity, not to headcount cost (reward-not-replace). Executive hours are a floor, not the case. The model measures seven dimensions; the contracted pair is instrumented against the buyer's own records before day 1, and dollarized only at the buyer's own stated rate (or reported raw if the buyer declines to dollarize).

**Every input below is tagged ASSUMPTION with a stated range. Ranges are candidates until the design-partner baseline confirms them; the STRUCTURE is the deliverable, the magnitudes are the negotiation.**

| # | Dimension | Formula | Key inputs (ASSUMPTION, with range) |
|---|---|---|---|
| D1 | **Workflow cycle time** | (baseline cycle time per instance minus pilot cycle time per instance) times instances per period times dollarized value of that time | cycle-time reduction 20-60% ASSUMPTION; instances/period from baseline; time value at buyer's own rate |
| D2 | **Decision latency** | (baseline request-to-decision elapsed minus pilot elapsed) on the one gated workflow times decisions per period times cost-of-delay per unit time | latency reduction 30-70% ASSUMPTION; cost-of-delay buyer-stated ASSUMPTION (often qualitative) |
| D3 | **Rework** | (baseline rework rate minus pilot rework rate) times units per period times cost per rework instance | rework-rate delta 10-40% ASSUMPTION |
| D4 | **Quality** | (baseline defect-escape rate minus pilot defect-escape rate) times cost per escaped defect; where not dollarizable, a tracked quality index instead | defect-escape delta 10-30% ASSUMPTION; index used when no dollar value agreed |
| D5 | **Missed commitments** | (baseline overdue-commitment count minus end-state count) times value-at-risk per missed commitment; count-only when value-at-risk is not agreed | overdue-count delta toward zero ASSUMPTION; MEASURED n=1 analogue: 39 cleared |
| D6 | **Adoption** | weekly active participation as a share of the designated cohort; a durability gate, not a dollar line: it multiplies whether D1-D5 persist | adoption 50-70% weekly-active ASSUMPTION; below the floor, the other savings are treated as unproven |
| D7 | **Capacity redeployment** | (executive plus team hours recovered) times the value of the higher-value work that capacity is redeployed into; NOT headcount removed | 3-6 hrs/wk exec recovered ASSUMPTION (MEASURED n=1 analogue); redeployment value buyer-stated ASSUMPTION |

**Why executive hours alone cannot carry it:** hours recovered (part of D7, dollarized at the buyer's rate) is the single most legible line, but it is one of seven and it is the easiest to dismiss as soft. A defensible ROI reads across the set: a workflow that runs faster (D1), decides sooner (D2), with less rework (D3) and fewer escaped defects (D4), where commitments stop slipping (D5), the behavior actually sticks (D6), and the recovered capacity goes to work that matters (D7). The contracted metric pair is D7 (hours) plus D5 (missed commitments), because both have MEASURED internal analogues and both are auditable by the buyer's own records; D1-D4 are secondary instrumentation that strengthen the case where the workflow supports them.

**Dollarization rule (honest math):** hours and outcomes are dollarized ONLY at the buyer's own stated rate, agreed at kickoff, never at an asserted market rate. If the buyer declines, the model reports raw units (hours, counts, elapsed times). A falsifiable baseline is a precondition; no baseline, no ROI claim.

---

## 3. Buyer outcomes vs seller outcomes (kept explicitly separate)

These two ledgers are never blended. The buyer is sold on the left column only; the right column is our economics and belongs in the achievement ledger, never in the buyer's ROI case.

| Buyer outcomes (what the buyer buys) | Seller outcomes (our economics) |
|---|---|
| Cycle time compressed, decision latency down (D1, D2) | A signed 90-day pilot: the raise trigger and the first ledger entry |
| Rework and escaped defects down (D3, D4) | Conversion to the companion retainer at day 91 |
| Missed commitments cleared and held (D5) | Referenceability a known investor can verify directly |
| Adoption that sticks, felt as reward not threat (D6) | Domino-2 pull inside the same account (the GTM ladder demonstrated once) |
| Executive and team capacity redeployed to higher-value work (D7) | Reusable-playbook percentage: the asset that converts service to software |
| A production-grade, human-gated workflow they keep | Gross-margin trajectory along the forward-deployed curve (section 5) |
| The head start: first across the adoption gap in their vertical | Cash actuals that let the model's ASSUMPTION ranges become MEASURED |

**The discipline:** never pitch the buyer on the seller's outcomes (their pilot is not sold as "your signature funds our raise"), and never book a seller outcome as buyer ROI (our reusable-playbook gain is not the buyer's savings). The two columns move on separate evidence.

---

## 4. Revenue architecture and the pilot fee scaffold

### 4a. Consult-versus-software split by domino

| Stage | Revenue type | Margin character | Basis |
|---|---|---|---|
| Domino-1 (chief-of-staff seat) | Consulting-margin delivery, operator-capacity-bound | Services band (section 5), high touch | MEASURED $25,000/mo retainer precedent (one client, unnamed) |
| Domino-2 (engineering overhaul) | Blended: repeatable delivery informed by Carter Razink's Recurro framework (his framework, an input to the engineering pillar, not the product) | Improving as playbooks harden | VENDOR precedent for outcome-shaped engineering pricing: Cognition/Devin, PRs merged, $492M ARR run-rate |
| Domino-3 (whole-org software) | Software subscription (per-seat or per-org) plus retained advisory | Approaches the hybrid band as recurring share rises (designed, horizon) | VENDOR: stacked OKR + gamification $20-50/user/mo; enterprise-assistant ACV $200-600K/yr at mid-market headcounts |

The split is the whole thesis of the P&L: domino-1 is a service, domino-3 is software, and domino-2 is where the conversion happens. Software margin is named in the future tense throughout.

### 4b. The pilot fee scaffold (setup + monthly + equity; never per-seat)

The scaffold shape is the deliverable; the numbers are a founder decision. Anchored to the value of a chief of staff plus an engineering lift, never to seats.

| Component | What it covers | Anchor (citable) | The number |
|---|---|---|---|
| **Setup fee** (one-time) | Baseline instrumentation, capture go-live, the one gated-workflow build | VENDOR: AI proof-of-concept $20K-250K; AI pilots $50K-200K over 8-16 weeks | Founder sets; concessionary for a design partner |
| **Monthly fee** (across the 90 days) | Design-partner delivery: capture + one gated workflow, then gamification entry | VENDOR: fractional chief of staff $7-14K/mo (up to ~$17K at full scope); full-time true cost $240-265K+/yr; anchored on the MEASURED $25K/mo precedent for the post-pilot retainer | Founder sets; internal working bands live in `pricing-model-options.md`, [unverified], off all external surfaces |
| **Equity component** (conditional) | Deepest-scope engagements only; the counsel default is equity plus cash, cash-only requires partner sign-off | Category precedent for equity-for-transformation exists (venture-studio and JV mechanics, VENDOR); sizing is counsel territory | Founder plus counsel set; no number proposed anywhere |

**The anchor sentence (external-safe):** the engagement is priced against what a chief of staff plus an engineering lift is worth to this executive, not against a seat count. The chief-of-staff anchor is VENDOR-citable; the engineering-lift anchor references an internal benchmark whose methodology memo is pending and is never a customer promise (R4).

---

## 5. The pilot P&L (single pilot; full founder cost; no hockey stick)

One pilot, ninety days. Revenue is the founder-set scaffold (section 4b); the cost side is real and estimable now. This is the only P&L that goes external, and it stays a single-pilot model.

**Revenue (per pilot, 90 days):** setup fee (one-time) + monthly fee times 3 + optional equity component. All founder-set; anchored per section 4b.

**Cost (per pilot, 90 days), the honest lines:**

| Cost line | Character | Tag |
|---|---|---|
| Fully loaded founder delivery time | The largest line and the binding constraint; single-operator capacity | ASSUMPTION (founder's own loaded rate times pilot hours) |
| Model / inference / infrastructure | Per-run compute for capture, agents, scoring | ASSUMPTION (metered; small next to founder time) |
| Tooling and third-party capture licenses | Otter/Fireflies-class capture, storage, embeddings | VENDOR ($10-30/user/mo class) |
| Originating-member contribution | Nick (gamification), Carter (engineering); equity-earning, not cash payroll at pilot stage | ASSUMPTION (contribution-for-equity, per decision 0003) |

**Pilot gross margin** = (pilot revenue minus the above) as a percentage. Because the pilot fee is not yet set, this margin is MODELED under the ASSUMPTION cost lines above and held to its stated range, never a current-state number. It sits in the services band (section 5b), NOT a SaaS band, because founder delivery time dominates the cost line. The pilot is deliberately concessionary for a design partner; the point of the pilot P&L is to show it is a real, costed engagement with the founder's own time fully priced in, not a loss leader disguised as a product.

### 5b. The forward-deployed margin shape (service becoming software)

The margin story is a trajectory, not a level. It is anchored to real market bands and explicitly capped short of mature-SaaS assumptions.

| Delivery stage | Honest gross-margin band | Basis (VENDOR) |
|---|---|---|
| Pure services (pilot, early domino-1) | 30-50% | IT services 25-35%, boutique 20-40%, MBB 45-55% |
| Hybrid, reusable playbook accumulating (domino-2) | services band widening as repeatable delivery rises | recurring share below ~30% keeps services-grade economics |
| Product-formation crossing the threshold (domino-3, horizon) | expands only as recurring software revenue crosses ~30%, then ~50%, of total | at >50% recurring, priced on hybrid-to-software multiples |
| The existence proof of the shape | Palantir 84-88% via forward-deployed work encoded into reusable platform IP | VENDOR; cited as the shape, never as our current margin |

**The a16z discipline (VENDOR), stated plainly:** the failure mode is pretending to be SaaS while actually being services with a platform. This model refuses that pretense. Margin expansion is earned only as the reusable-product percentage rises; until then the economics are services economics, and the model says so.

---

## 6. The 24-month model: three branches (internal capacity-and-survival model, NOT a revenue projection)

This model exists to answer one question: does the company survive, and stay in the founder's control, across 24 months under each scenario. It is scenario planning on five levers, not a growth curve. It is internal; the external surface remains the pilot P&L only. It carries this label wherever it travels.

**The five levers:** (1) pilot conversion (does the pilot convert to a retainer at day 91), (2) sales cycle (how fast the next design partner signs), (3) founder capacity (the single-operator constraint), (4) implementation burden (how bespoke each engagement is), (5) reusable-product percentage (how much of delivery converts to reusable IP and, eventually, software margin).

| Lever | Downside | Base | Upside |
|---|---|---|---|
| Pilot conversion | Pilot does NOT convert (failed pilot) | Converts to retainer | Converts fast, referenceable |
| Sales cycle | Long; no second partner in-window | One additional design partner | Multiple partners, relationship-compressed |
| Founder capacity | Fully consumed by delivery | Supplemented by originating-member contribution | Extended as playbooks harden |
| Implementation burden | High, fully bespoke | Falling as playbooks form | Largely productized for common workflows |
| Reusable-product % | Low; stays services | Rising modestly | Crosses the recurring-revenue threshold (software margin begins, horizon) |

**Downside branch (the one that must survive a failed pilot).** If the pilot fails to convert, the company still stands, for reasons independent of the pilot: (a) the strategic check is sized as runway to the month-6 milestone with contingency (section 8), not as a bet on one conversion; (b) the founder's existing consulting book already generates services revenue independent of the product (MEASURED $25,000/mo precedent among active engagements); (c) full founder cost is already in the model, so there is no hidden capacity cliff to fall off; (d) a failed pilot still produces a MEASURED baseline, a costed engagement, and lessons that sharpen the next design-partner offer. Survival, not growth, is the downside metric. No revenue line hockey-sticks in any branch.

**Base and upside branches** differ only in how fast conversion, the next signing, and reusable-product percentage move. In every branch: full founder cost is included, no mature-SaaS margin is assumed, and software margin appears (if at all) only at the tail and only as the reusable-product percentage earns it. The branches are bounded by founder capacity, which is why originating-member contribution and reusable-product percentage are the two levers that most change the shape.

**What the branches are NOT:** they are not three revenue projections to wave at an investor. The counsel rule is pilot P&L only externally; this section is the internal discipline behind the single external number, and it is labeled as a survival model every place it is referenced.

---

## 7. The day-91 conversion trigger (what turns the pilot into an annual contract)

The pilot converts to an annual companion retainer at day 91 when, and only when, the day-90 gate clears on buyer-verifiable evidence. This is an evidence threshold, not a sales close.

**All of the following must hold at the day-90 gate:**

1. **Sustained capacity recovery (D7 / B1):** executive hours recovered holding across 4+ consecutive weeks, confirmed in the buyer's own records.
2. **Missed-commitment debt cleared (D5 / B2):** overdue-commitment count at or near zero and staying there.
3. **Graduation status honest:** at least one decision class at or past the 90%-agreement-over-20+-reps bar (with the executive's written sign-off per class), OR a documented honest reason it is not yet appropriate. Classes touching money, irreversible, or external actions do not graduate within the pilot.
4. **The buyer's own baseline confirms the ROI** on the contracted metric pair (D7 + D5). No baseline confirmation, no conversion claim.
5. **Zero ungated money, irreversible, or external actions** across the entire pilot. This is a hard requirement; a single ungated action fails the gate regardless of everything else (product law).
6. **CEO personal ownership sustained** through weekly check-ins.

**Day 91:** the buyer converts to the companion retainer (annual), grants a defined referenceability scope, and opens the domino-2 sponsorship conversation. The retainer band is anchored on the MEASURED $25,000/mo precedent; the number is a founder decision and stays off external surfaces until confirmed.

---

## 8. Domino-trigger metrics per GTM stage

Each stage advances only on its own evidence. These are the metrics that open the next door; they are not the ROI (section 2) and not the seller ledger (section 3), though they draw on both.

| Stage | Trigger to advance | Metric that opens the next domino |
|---|---|---|
| **Domino-1 -> Domino-2** | Day-90 gate cleared (section 7): capacity recovered, commitments cleared, workflow in production, zero ungated actions, conversion signed | 90 days of gated agent work on the CEO's own calendar, plus a CEO-made internal referral to the CTO / VP Engineering |
| **Domino-2 -> Domino-3** | Domino-1 gate cleared first (hard precondition). Engineering engagement instrumented like domino-1: baseline, named owner, kill criterion | Engineering throughput, cycle time, and cost-per-shipped-unit on the buyer's OWN definition, moving on a signed baseline. The engineering-lift anchor references an internal benchmark, methodology pending, never a customer promise (R4) |
| **Domino-3 (whole-org software)** | Playbooks hardened into reusable product; per-org or per-seat software pricing displaces bespoke delivery | Recurring-software revenue share crossing ~30%, then ~50%, of account revenue (the margin-multiple thresholds, section 5b). This is the point at which the service has become software |

The ladder is demonstrated once inside the first account; that single demonstration, not a projection, is what the achievement ledger records.

---

## 9. Strategic-check sizing method (method, not a number)

The strategic check is the "smaller strategic check" of the canonical ask. Its size is a founder-plus-counsel decision; the METHOD is the deliverable, and no band appears in any external material.

**Method:**

    strategic check  =  six-month milestone budget
                        (fully loaded runway to the ~month-6
                         demonstrated-achievement milestone that
                         triggers the larger raise)
                      +  contingency
                        (the 20-40% AI-engagement overrun anchor, VENDOR)
                      -  pilot revenue that offsets the same period

**Notes on the method:**
- It is a runway-to-milestone calculation, never a valuation-of-vision number. The check funds reaching the achievement that earns the larger raise; it does not price the company.
- Full founder cost is inside the six-month budget (governing law 5).
- Pilot revenue (section 5) reduces the check, so a converting pilot shrinks the ask, which is the honest direction.
- The pre-correction "$10-50M raise" framing is INVALID (CLAUDE.md correction 3) and is not carried here in any form.
- The two-transaction discipline holds (counsel addendum 3 B1): the strategic check (investment paper) and the pilot (services paper) are separate decisions on separate evidence; a yes to one is never a yes to both.

---

## 10. Reconciliation with numbers already stated externally

The spine must not contradict what the exec-overview and one-pager already put in front of a reader.

| Externally stated | Where | This spine |
|---|---|---|
| One consulting client at **$25,000/month** (MEASURED) | exec-overview, one-pager | The only MEASURED price point; the post-pilot retainer anchor. Client never named. |
| The canonical ask (verbatim) | exec-overview, one-pager, reading room | Section 9 sizes the strategic check by method; the ask sentence is used verbatim, never re-parametrized. |
| No throughput / 16x figure claimed | exec-overview ("no throughput figure is claimed") | Governing law 7; no multiplier anywhere in this spine. |
| Consulting-plus-software hybrid, equity + cash | exec-overview, one-pager | Sections 4-5; consulting first, software horizon, equity component conditional. |
| Reference implementation, fleet-of-one, not a customer | exec-overview, reading room | MEASURED analogues labeled n=1 reference implementation, never a client result. |

**Canonical ask, verbatim (for any artifact that cites the ask):** "A scoped 90-day design-partner pilot plus a smaller strategic check. The larger raise comes at roughly month 6, triggered by demonstrated achievement."

---

## 11. Open questions only the founder can answer

Everything below is a founder decision; none of it appears with a number in any external artifact until confirmed.

1. **The pilot fee number itself** (setup + monthly), within or outside the internal `$45-60K`/90-day working band [unverified].
2. **The post-pilot companion retainer band** (internal `$20-30K/mo` working band anchored on the MEASURED $25K/mo) [unverified].
3. **Whether this first pilot carries an equity component** or is cash-only under the counsel partner-sign-off exception.
4. **The strategic-check number** (via the section 9 method), and the instrument (SAFE / note / priced), both founder plus counsel.
5. **The ROI ranges in section 2** as the contract's target magnitudes; they stay ASSUMPTION until the design-partner baseline signs them.
6. **The firmographic band** ($50M-$3B revenue, mid-market posture) and CEO-only vs any-C-level as a deliberate choice rather than a research inheritance.
7. **Vertical concentration** (if any) for the first design partners, versus staying vertical-agnostic.

*End of spine. The designed surface is `index.html`; the internal detail behind each number lives in `07-roadmap/W8-unit-economics/` and `07-roadmap/W7-pilot-design/`.*
