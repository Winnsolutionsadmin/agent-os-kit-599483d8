# Design-partner qualification: profile matrix, scoring rubric, and second-partner scorecard

**Wave-2 meeting-pack artifact.** Purpose: give the founder a repeatable screen for who the first pilot wants, and give a known investor a precise picture of exactly which company to introduce. This is the "who to introduce" instrument, not a sales list.

**Authored:** 2026-07-09. **Built on:** the unit-economics spine (`09-deliverables/financials-icp/source.md`, section 1, the ICP as firmographics) and the roadmap pilot design (`07-roadmap/W7-pilot-design/`). It distills them; it does not restate them.

**Governing discipline (fixed):**
- **Firmographics, not the go-to-market motion.** The domino sequence (C-levels, then engineers, then everyone else) is the *order* we sell in. This profile is the *company shape* a stranger could screen against. Only the firmographics belong here.
- **Two transactions, never blended.** The design partner is the operating counterparty on the 90-day pilot. The investor is a separate decision on separate paper. If the known investor is also the counterparty, the pilot charter goes on the table; if not, the investor sources the introduction. A yes to one is never a yes to both.
- **Never invent candidates.** Every company cell in the shortlist is left as `[ founder fills ]`. The matrix is the screen; the founder and the investor populate the rows.
- **Read-only pilot boundary.** The pilot captures and reads real operating surfaces; it does not act on money, irreversible, or external actions. Data-access readiness is screened against that boundary.

Lineage tags used below: MEASURED (instrumented first-party or signed engagement), SURVEY (third-party study), VENDOR (vendor-published or third-party-reported market figure), CORPUS (internal build, self-reported), ASSUMPTION (stated design estimate), [unverified] (founder decision pending).

---

## 1. What a design partner is (and is not)

The design partner is the **named operating counterparty** of the 90-day pilot: the company whose real work the system captures, scores, and helps run under a human gate. A complete counterparty has nine named fields: operating counterparty, executive sponsor, workflow owner, data owner, baseline, success threshold, kill criterion, fee, and the day-90 decision. A candidate that cannot fill those nine fields is a prospect, not yet a partner.

The design partner is distinct from the investor. The pilot is a services decision on its own paper; the strategic check is an investment decision on its own paper. The most useful thing an investor who is *not* the counterparty can do is introduce a company that scores well on the matrix below.

---

## 2. Design partner #1: the qualification matrix

Six dimensions. Each carries what qualifies, the basis, and the fast disqualifier that ends the conversation.

| Dimension | What qualifies | Basis | Fast disqualifier |
|---|---|---|---|
| **Firmographic band** | Mid-market, roughly $50M-$3B revenue, lean executive team, an internal engineering org present for the second domino | VENDOR/press: the lab and systems-integrator mid-market pushes target this band; positioned below the large-enterprise tier the global SIs serve first. Band is [unverified], a founder decision | Enterprise so large that procurement, not the executive, owns the buy; or so small there is no real operating load to compress |
| **Buyer role** | The CEO personally, or a COO/President who fully owns operations, as the domino-1 seat; a CTO or VP Engineering with the CEO as internal sponsor for domino-2 | SURVEY: CEO personal ownership with weekly check-ins is the single strongest success predictor across 51 enterprise AI deployments (Stanford Digital Economy Lab) | The buyer is a delegate with no operating authority, or an innovation-lab budget with no line ownership |
| **Trigger condition** | The executive is personally the bottleneck: overflowing meeting load, follow-up debt that never clears, status and reporting assembled by hand, and a board asking for an AI story | MEASURED n=1 analogue (reference implementation, not a customer): overdue follow-ups cleared and hours recovered for one operator; generalization [unverified] | No acute pain the executive feels this month; a "someday, in principle" interest |
| **Data-access readiness** | Willing and able to grant read-only access to real operating surfaces (calendar, meetings, objectives) within a written consent and retention boundary, and to sign a falsifiable baseline plus a kill criterion | The pilot capture path is read-only by design; a falsifiable baseline is a precondition for any ROI claim | Disclosure-sensitive capture scope (legal, board, M&A) demanded before a data-governance posture exists; refusal to sign a baseline or a kill criterion |
| **Executive-sponsor availability** | A named executive sponsor (ideally the CEO) commits to weekly check-ins for the full 90 days | SURVEY, same Stanford finding: sustained executive ownership is the durability gate on every other outcome | Sponsor cannot commit weekly time; ownership is nominal, delegated on day one |
| **Disqualifiers (screen fast)** | None of the below present | ICP disqualifier set | See the standalone list under section 2a |

### 2a. Hard disqualifiers (any one ends it, regardless of score)

- The CEO will not personally own it.
- Replace-not-reward intent: headcount reduction is the headline the buyer wants.
- Demands day-one autonomy on money, irreversible, or external actions (violates product law).
- Will not sign a baseline and a kill criterion.
- Procurement-led cold buying with no warm path.
- Disclosure-sensitive capture scope before the data-governance posture exists.
- A live customer-facing crisis consuming the executive.
- (Soft, caps rather than kills) No engineering org, which limits the account to the chief-of-staff seat because the second domino has nothing to land on.

---

## 3. Scoring rubric

Six scored dimensions, each rated 0 to 3, each weighted. Any hard disqualifier from section 2a sends the candidate to "pass" regardless of the total.

**The 0 to 3 scale:** 0 absent, 1 weak, 2 present, 3 strong and evidenced.

| # | Scored dimension | Weight | What a 3 looks like |
|---|---|:---:|---|
| 1 | Executive sponsor: CEO personal ownership plus weekly check-ins committed | 3 | The CEO names themselves the sponsor and blocks the weekly time in writing |
| 2 | Trigger intensity: the executive is acutely, nameably the bottleneck this month | 2 | The pain is specific, current, and the executive can quantify it unprompted |
| 3 | Data-access readiness: read-only access to real surfaces within a consent boundary, baseline and kill criterion signable | 2 | Access and a falsifiable baseline are both agreeable now, not "after legal" |
| 4 | Reward-not-replace intent: framed as capacity gained, not headcount cut | 2 | The executive wants their team stronger, not smaller, and says so |
| 5 | Firmographic fit: mid-market band, lean executive team, engineering org present | 2 | Squarely in band, with an engineering org for the second domino |
| 6 | Referenceability: willing to be a verifiable reference a known investor can call | 1 | Agrees in principle to a defined referenceability scope at day 91 |

**Maximum weighted score:** (3 + 2 + 2 + 2 + 2 + 1) times 3 = **36**.

**Bands:**

| Total | Band | Meaning |
|---|---|---|
| 30 to 36 | **Ideal** | Lead the pilot conversation here; charter-ready |
| 22 to 29 | **Qualified** | A real candidate; name the one or two gaps and close them before signing |
| 14 to 21 | **Conditional** | Interesting but with a structural gap (usually sponsor time or data readiness); do not paper until it clears |
| below 14, or any hard disqualifier | **Pass** | Not a design partner; do not spend the window here |

The score is a screen, not a verdict. Dimension 1 is weighted highest because sustained executive ownership is the one factor the outcomes research treats as decisive; a candidate strong everywhere except dimension 1 is still a Conditional, not an Ideal.

---

## 4. Design partner #2: the qualification scorecard

The second design partner is scored on the same six dimensions **plus four second-partner gates**. The point of a second partner is a second, independent data point, so a copy of the first partner is worth less than a partner that diversifies the evidence. This is a per-candidate scorecard the founder fills.

**Candidate:** `[ founder fills ]`

| # | Dimension | Weight | Score (0 to 3) | Note |
|---|---|:---:|:---:|---|
| 1 | Executive sponsor (CEO ownership, weekly check-ins) | 3 | `[  ]` | `[ founder fills ]` |
| 2 | Trigger intensity | 2 | `[  ]` | `[ founder fills ]` |
| 3 | Data-access readiness within the boundary | 2 | `[  ]` | `[ founder fills ]` |
| 4 | Reward-not-replace intent | 2 | `[  ]` | `[ founder fills ]` |
| 5 | Firmographic fit | 2 | `[  ]` | `[ founder fills ]` |
| 6 | Referenceability | 1 | `[  ]` | `[ founder fills ]` |
| | **Weighted total (of 36)** | | `[  ]` | Band: `[ founder fills ]` |

**Second-partner gates (each yes or no; a "no" on any of the first three is a reason to defer, not disqualify):**

| Gate | Why it matters | Yes / No |
|---|---|---|
| **Signal diversity:** a different vertical or a different workflow class than partner #1 | Two partners in the same shape give one data point, not two; diversity is what makes the second pilot evidence rather than repetition | `[  ]` |
| **Non-competition with partner #1** | Referenceability, lessons, and captured context must not leak between two competitors | `[  ]` |
| **Sequencing:** onboarding lands *after* partner #1 is stable, not across its day-90 gate | The single-operator founder capacity is the binding constraint; two pilots peaking together is the failure mode | `[  ]` |
| **Intro path named** (warm, and if investor-sourced, from whom) | A second partner reached cold restarts the whole procurement clock; a warm path is the whole advantage | `[  ]` |

**Reading the scorecard:** a second partner should be Qualified or better on the six dimensions AND clear the first three gates as yes, OR carry an explicit, dated plan to make them yes before the pilot starts. A high score with a "no" on sequencing is a good partner at the wrong time; hold it.

---

## 5. Ranked shortlist (structure only)

The structure is the deliverable. **Every candidate cell is left for the founder and the investor to populate. No candidate company is invented here.**

| Rank | Candidate company | Firmographic band | Buyer (role, not name) | Trigger observed | Warm / intro path | Weighted score | Band | Status |
|:---:|---|---|---|---|---|:---:|---|---|
| 1 | `[ founder fills ]` | `[ founder fills ]` | `[ founder fills ]` | `[ founder fills ]` | `[ founder fills ]` | `[  ]` | `[  ]` | `[  ]` |
| 2 | `[ founder fills ]` | `[ founder fills ]` | `[ founder fills ]` | `[ founder fills ]` | `[ founder fills ]` | `[  ]` | `[  ]` | `[  ]` |
| 3 | `[ founder fills ]` | `[ founder fills ]` | `[ founder fills ]` | `[ founder fills ]` | `[ founder fills ]` | `[  ]` | `[  ]` | `[  ]` |
| 4 | `[ founder fills ]` | `[ founder fills ]` | `[ founder fills ]` | `[ founder fills ]` | `[ founder fills ]` | `[  ]` | `[  ]` | `[  ]` |
| 5 | `[ founder fills ]` | `[ founder fills ]` | `[ founder fills ]` | `[ founder fills ]` | `[ founder fills ]` | `[  ]` | `[  ]` | `[  ]` |

Rank by weighted score first, then by warmth of the intro path as the tie-breaker (a warm path compresses the procurement clock, which is the scarce resource in the window). Keep the list short: five rows is a shortlist, not a database.

---

## 6. How the investor uses this

If the known investor is the operating counterparty, section 1's nine fields become the one-page pilot charter and the conversation is about filling them. If the investor is not the counterparty, the single most valuable ask is: "Given this profile, who in your portfolio or network fits row 1?" The matrix is written so a stranger to the venture can screen a company against it without asking the founder a single follow-up question. That property is the whole point: it turns a warm relationship into a specific, sourceable introduction.

*End. The pilot mechanics behind each field live in `07-roadmap/W7-pilot-design/`; the firmographic reasoning lives in `09-deliverables/financials-icp/source.md`.*
