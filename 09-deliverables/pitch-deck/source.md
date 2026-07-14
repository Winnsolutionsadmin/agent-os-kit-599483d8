# Pitch deck: source content + speaker notes

**Deliverable:** 09-deliverables/pitch-deck | **Authored:** 2026-07-09 (recovery build) | **Recipient:** the 7/17-18 meeting (belief-indexed to Allan; slides forwardable, Allan-specific talk track in notes).
**Render:** `index.html` (self-contained HTML deck) is the client-facing artifact. This markdown is the content of record; the HTML renders it.
**Governing law:** repo `CLAUDE.md` corrections; `05-counsel/counsel-deepdive-2026-07-09.md` ADDENDUM 4 (R1-R8) > ADDENDUM 3 (S1-S4, B1-B11) > earlier addendums. See `_extract-notes.md` for the applied supersessions and the verbatim-quote ledger.
**Hard constraints baked in:** no em dashes; every stat lineage-tagged (MEASURED / SURVEY / VENDOR / CORPUS / ASSUMPTION); no 16x anywhere (R4); no throughput comparison at all (S1); no "3x/10x" band (S2); no multi-year projections; no model-panel badges (B5); no client names (gate C); fleet-of-one labeled reference implementation (gate D); corpus + registry are inputs, not traction (gate E); no slide implies an executed agreement (B10); "agent OS" is a lowercase descriptor only (S4).

**Count:** 13 core slides + 3 appendix. One beat per slide. Every list holds 2-3 items (VOICE_SPINE).

---

## Slide 1: Cover

**On slide:**
- Wordmark: `[ NAME ]` (brackets are the motif; the fill is a deliberate blank).
- A trusted companion for the AI transition.
- Descriptor line: a gamified, AI-powered operating system for organizations. Presented unnamed by design.
- Prepared for the 7/17-18 meeting. Jarred Winn, founder. July 2026.

**Speaker notes:**
No stats on the cover. Open the unnamed status out loud, approved script (S3, S4): "The product is intentionally unnamed. I'll choose the permanent mark from a legally cleared shortlist after the position is locked. For today, the working descriptor is agent OS for organizations. The decision in front of us is the 90-day design partnership, not a wordmark." The bracket motif carries continuity with the reading room, one-pager, and exec overview. Do not say "brand in stealth."

## Slide 2: The problem is adoption, not capability

**On slide:**
- Capability is arriving. Adoption is not.
- 94% of knowledge workers already use AI at work. But disclose that you used it, and a controlled experiment rated you 10x lazier and 24 percentage points less likely to be picked for high-visibility work, at identical output (SURVEY, Atlassian 2026).
- The field is wide open: 62% of orgs are experimenting, about 23% have scaled even one system into production, and full agentic operation is rarer still (SURVEY, McKinsey Nov 2025).
- Cost of doing nothing: every quarter you wait, shadow AI spreads ungoverned and the head start compounds to whoever crosses first.

**Closing line (on slide):** The company that makes its people safe to use AI takes the vertical. Nobody's selling that yet.

**Speaker notes:**
This is the problem statement, belief-indexed to an operator: the blocker is human, not technical, so the fix is organizational psychology, not more model. Tags: Atlassian disclosure penalty = SURVEY (controlled experiment, 2026). McKinsey 62% experimenting / ~23% scaled one system = SURVEY (Nov 2025). Do NOT round to a "1%" hero stat, do NOT revert to the "~6% high performers" cut (R7), and do NOT invoke any "3x/10x" band (S2). "Shadow AI" is the sprawl he already feels in his own portfolio. Keep it to two numbers; he takes the smaller sourced number over the bigger shrug.

## Slide 3: The wedge, and why this founder

**On slide:**
- Concede it plainly: Anthropic and its peers can build the capability. That's the market premise, not our fear.
- The wedge is a C-suite that finally has a chief of staff which never sleeps. Then engineering wants the overhaul. Then the rest is pulled in by demand.
- The proof isn't a roadmap. Jarred runs the reference implementation today, at fleet-of-one scale. This operation is the demonstration.

**Closing line (on slide):** Companies don't need another platform. They need a companion that gets the whole building to actually use one.

**Speaker notes:**
Founder track record lands by slide 3 (ADDENDUM 2). "Reference implementation," never an installed customer (gate D). Trusted-companion positioning (correction 7, decision 0003). Domino GTM order is fixed (correction 8): C-levels first (chief of staff / organizer), engineers next (revamp / overhaul), all else by demand. The engineering domino draws on Carter's own agentic-engineering framework as an input to the pillar; do not name it as a product. No "I built" bragging; show the running system, let it speak.

## Slide 4: The ask, up front (so you read the rest through it)

**On slide:**
- I'm asking for two separate decisions.
- Canonical ask: A scoped 90-day design-partner pilot plus a smaller strategic check. The larger raise comes at roughly month 6, triggered by demonstrated achievement.
- The pilot is your operator seat. The check is your owner seat. Papered separately, never blended.

**Closing line (on slide):** Read everything after this through that ask. The evidence is sized to it.

**Speaker notes:**
R5: name the two-transaction ask in the first ~4 minutes as ORIENTATION, then spend the middle on premise plus the single demo trace so the evidence is read through the ask, then re-land the concrete dated step at close (slide 13). Canonical sentence is verbatim, identical across every artifact (ADDENDUM 1.1). Two-transaction separation is a hard rule (B1): a yes to one is never a yes to both. Ownership framing is belief-fit (recipient belief 4): operator seat + owner seat at evidence-matched scale. No instrument, no size, no fee spoken here or anywhere on a slide.

## Slide 5: One trace, end to end (the signature)

**On slide:** a faithful rendering of one real, redacted trace from the running estate, read top to bottom. Each field is filled from the frozen 7/12 trace.
1. Source sentence: "[ filled from the frozen 7/12 trace ]"
2. Freshness timestamp: `[ filled from the frozen 7/12 trace ]`
3. Stable locator / hash: `[ filled from the frozen 7/12 trace ]`
4. Context retrieved: the related objective from the OKR tree, plus the prior notes it cites by locator.
5. Recommendation: create a task and a CRM entry. Sourced to the sentence and the objective. One field flagged low-confidence: owner, please confirm.
6. Human gate: `[ Approve ]` `[ Edit ]` `[ Skip ]`. The executive decided.
7. Audit receipt ID: `[ filled from the frozen 7/12 trace ]`. Append-only: who decided, timestamp, elapsed from spoken to surfaced.
8. Replay steps: `[ filled from the frozen 7/12 trace ]`. The exact sequence to reproduce this readout from the frozen source.
9. Boundary: it detected, retrieved, rendered, and appended. It did not send anything, and it did not act outside the gate.

**Caption (on slide):** Rendering of a real trace; frozen source and receipt attached in the demo pack.

**Closing line (on slide):** Every output arrives sourced, and stops at a person. That's the product.

**Speaker notes:**
Lead the whole deck and the demo narration with this ONE trace (R6, B3). It is a faithful rendering of one real redacted trace: the placeholders are filled from the frozen 7/12 trace (H1) before any send, so the founder drops in the real source sentence, locator or hash, freshness stamp, receipt id, and replay steps. It is grounded in the built meeting-capture pipeline (C1 in `W7/days-1-30-plan.md`); the estate counts that evidence the pipeline (343 notes, 47k embeddings, 5 real tasks from one meeting, all MEASURED, n=1) live in Appendix C, not in this core trace. The low-confidence field is the deliberate uncertainty moment (R3): the system shows what it isn't sure of instead of hiding it. The boundary line is the honest B2 truth: the current spike detects, renders, appends, and stays idempotent; it is not yet closed-loop relay, so never narrate it as an agent consuming its answer and continuing. Elapsed-time figure is estate telemetry, n=1; if a specific number isn't logged for this trace, say "surfaced while the meeting was still live" rather than assert a latency.

## Slide 6: What's real, in four columns

**On slide:** every visible capability, classified. An outside reviewer can place each one without asking me.

| Operating internally | Prototype | Pilot build (the 90 days) | Horizon |
|---|---|---|---|
| Meeting capture to tasks | Front-door triage surface | Capture live in one org | Skill marketplace |
| OKR alignment scoring | Pre-meeting briefing packs | One gated workflow in production | Attribution / proof-of-origination |
| Achievement engine | | Gamification for an opt-in cohort | |
| Fleet HUD, skill registry | | The signed baseline | |

**Closing line (on slide):** Built things run. Designed things are named as designed. No blur.

**Speaker notes:**
B4 requires exactly this four-column truth table, in the deck and the overview, with every capability classifiable by an uninvolved reviewer. Built-vs-designed is a hard rule (ADDENDUM 1.2): nothing designed-but-unbuilt speaks in the present tense. "Operating internally" is the fleet-of-one reference implementation (gate D), not a customer. "Horizon" items are designed, not running (attribution is the least-built pillar, zero code today). The activity counts behind these live only in the appendix (R6).

## Slide 7: How autonomy works: the human holds the gate

**On slide:**
- The system does the work. The human holds the gate.
- `[ Approve ]` `[ Edit ]` `[ Skip ]`. Nothing that touches money, an outside party, or anything irreversible moves without a person deciding.
- Autonomy is earned, not granted: an advisor acts on a decision class on its own only after it has matched your actual choice at least 90% of the time across at least 20 reps. No tier buys an exception.

**Closing line (on slide):** Autonomy is earned in reps, never sold in tiers.

**Speaker notes:**
Product law, "don't touch it" (counsel-kept 4/4). Graduation source: `01-overview:54`. Frame this as risk-reduction structure, his stated preference, not compliance overhead (recipient directive 4). This slide doubles as the pre-answer to the surveillance and agent-risk objection before it's raised. Autonomy overclaim gate: the system orchestrates, humans execute the final gate; never "runs your company."

## Slide 8: The live inspection: what you'll see, and what you won't

**On slide:**
- In the room: one sourced estate readout, live and READ ONLY. A real source event, its provenance, a freshness timestamp, one moment where the system says what it isn't sure of, then 2 or 3 questions you pick from a cleared set, answered with citations.
- What it will not do: no writes, no sends, no action-shaped buttons. The READ ONLY label stays up the whole time.
- Honest on the spike: today it detects, renders, appends, and stays idempotent. It doesn't yet consume its own answer and keep going. When it does, you'll watch that happen, not hear me claim it.

**Closing line (on slide):** If a demo has to pretend to be live, the trust is already gone. This one won't pretend.

**Speaker notes:**
R3 sets demo scope; B2 sets demo agency law. POST routes disabled, write credentials removed, persistent READ ONLY label, provenance and freshness visible, narrate only the observed data path, timestamped recording as the honest fallback. The four published demos are the watch-it-happen assets (CORPUS, at winnsolutionsadmin.github.io/allan-ai-demos/): an agentic treasury desk, a 20-vehicle registration agent with dollar-approval cards, the front-door triage pattern, and a full day run by text. Two were built against Allan's own pains (fleet registration, treasury visibility), which is why the visual language is his. The single real product view on this slide is a framed rendering of the running surface; OPEN ITEM: drop a live screen capture in before send.

## Slide 9: The boundary of the pilot

**On slide:**
- During the pilot, the product turns one organization's meetings, objectives, and workflow state into sourced recommendations an executive can approve, edit, or skip.
- In scope: capture on a designated, disclosed surface, plus one gated workflow chosen with you in week one.
- Out of scope: undisclosed capture, ungated actions, anything you didn't sanction. Capture is always disclosed.

**Closing line (on slide):** One org, one workflow, one gate. Narrow on purpose.

**Speaker notes:**
The boundary sentence is on-slide verbatim (brief-supplied). Narrow scope is the deliberate design (Stanford 51-deployment SURVEY: 73% of successful deployments started small, `W7/days-1-30-plan.md`). "No undisclosed capture in any context" is must-have 7, the Winn.ai eviction lesson. The gated-workflow classes are all drawn from what the estate already runs; THE one is selected with the partner in week one by rubric, and that rubric is an internal tool, never on a slide.

## Slide 10: The 90-day pilot, day by phase

**On slide:**
- Days 1 to 30: capture goes live, plus one gated workflow in production. You sign a two-week time baseline and your day-zero follow-up debt. Zero ungated actions. Day-30 gate.
- Days 31 to 60: gamification enters for an opt-in cohort, anti-abuse on from its first day. Adoption gets measured. Day-60 gate.
- Days 61 to 90: the evidence holds or it doesn't. Hours recovered, follow-up debt near zero, at least one decision class at or past graduation or an honest reason why not. Then the conversion decision. Day-90 gate.

**Closing line (on slide):** You don't buy a promise. You sign a baseline, then watch it move.

**Speaker notes:**
Phasing is counsel-kept 4/4: capture + one gated workflow days 1-30, gamification 31-90. The 30/60/90 gate structure is the deliverable; every threshold number (90% capture coverage, 15+ gated executions, 60% adoption, 50% follow-up-debt cut, 3-6 hours/week recovered) is an [unverified] candidate until the partner signs the baseline (`W8/buyer-roi-model.md`), so keep numbers off the slide and in discovery. Before day 1: a signed baseline and a written kill criterion (day 1 is capture go-live, not signature). The kill criterion and baseline signing are risk-reduction structure, his language.

## Slide 11: The economics, as a shape

**On slide:**
- Consulting plus software. Consulting revenue funds the build and makes the evidence first. Software margin is layered on later, it doesn't lead.
- Priced against a job you'd otherwise hire, not a per-seat license. A full-time chief of staff runs $240-265K a year fully loaded; a fractional one $7-14K a month (VENDOR). The 90-day pilot is a fraction of that.
- The hurdle: the pilot clears it if it returns your hours and clears your follow-up debt, measured against the baseline you sign, dollarized at your own rate. No multiplier is sold.

**Closing line (on slide):** The margin story starts as a service, and earns the right to become software.

**Speaker notes:**
ADDENDUM 2 financials: pilot P&L shape only, no multi-year hockey stick; price anchored to a chief of staff plus an engineering lift, not per-seat SaaS. External anchors ($240-265K/yr true cost, $7-14K/mo fractional) are VENDOR (`W8/vendor-pricing-scan.md`, retrieved 2026-07-08), safe to show; our own fee is NOT on any slide. Working band lives in speaker notes only, [unverified], founder to set: a concessionary design-partner fee in the low-to-mid five figures for the 90 days, then a $20-30K/mo companion retainer post-pilot, anchored on one already-signed retainer at $25k/mo (MEASURED, client unnamed per gate C). The worked hurdle is the recipient's own capital logic (put the arithmetic on the page, recipient directive 1): hours recovered at his own rate versus a concessionary fee, plus a production workflow he keeps. No 16x (R4), no throughput comparison at all (S1), no per-account LTV asserted.

## Slide 12: The team, honestly

**On slide:**
- Jarred Winn, founder. The vision is his. He operates the reference implementation.
- Nick Metzler and Carter Razink, originating members, earning equity through contribution. Deliverable-tied, vested. Not a three-way split.
- Status, stated plainly: entity formation and IP assignment are in flight this week. Nothing here implies an agreement that isn't signed.

**Closing line (on slide):** One founder accountable. Two contributors earning in. No fictional org chart.

**Speaker notes:**
Correction 5 and decision 0003: Jarred is THE founder; Nick and Carter are originating members who EARN equity through contribution (small time-vested base plus milestone kickers, founder-picked mechanism). No "three founders," "founding partnership," "co-founder," or fixed-split language anywhere. B10: no slide implies an executed agreement; entity + IP assignment + the contribution-equity framework are due this week and are counsel-flagged survival-critical. Nick owns gamification mechanics (definition due 7/31); Carter's engineering framework is an input to the engineering pillar. Contributor agreements name the specific deliverables tied to each equity kicker.

## Slide 13: The ask, re-landed

**On slide:**
- The ask, again: A scoped 90-day design-partner pilot plus a smaller strategic check. The larger raise comes at roughly month 6, triggered by demonstrated achievement.
- If you're the operating counterparty: the one-page pilot charter goes on the table. Named owner, baseline, success threshold, kill criterion, day-90 decision. Next step, dated: a pilot scoping session on [ date, within 72 hours ].
- If you're the sponsor, not the operator: sponsorship plus the strategic check, plus a scoping session on [ date, within 72 hours ] to name who runs it.

**Closing line (on slide):** A pass keeps the relationship, and we come back with a signed partner's day-30 evidence, not a re-pitch.

**Speaker notes:**
R5 re-land: restate the canonical ask verbatim and name the concrete dated next step within a week. R8 two branches, both rehearsed before 7/17: investor-as-operating-counterparty (charter on the table) vs investor-as-sponsor (sponsorship + check + a dated scoping session within 72 hours). A fully signed pilot in the first meeting is not required or expected. Branch C (graceful pass) is stated as acceptable, which reads as "stay in lane" respect and keeps the relationship warm for the achievement-triggered raise later (recipient directive 5). Raise-trigger logic lives here in the notes, never on the slide: the signed pilot is achievement and the raise trigger; the check is faith; papered separately (B1). No instrument, size, or fee spoken.

---

# Appendix (on request, not in the 10-minute run)

## Appendix A: The architecture, arrows labeled

**On slide:** seven pillars, one system. Every connection is labeled by its state.
- Front door (the face). The one calm surface. State: prototype.
- OKR engine (the brain). Objectives to weighted, agent-run subtasks. State: built.
- Gamification (the adoption engine). Reward, do not replace. State: pilot-scope.
- Meeting capture (the senses). Transcripts to decisions, actions, memory. State: built.
- Client relationships (the channel, part of the moat). State: built.
- Skill marketplace (the network effect). State: designed.
- Attribution (the trust layer). Proof-of-origination. State: designed.

**Speaker notes:**
Gate B: each arrow is labeled built / pilot-scope / designed; no unlabeled bidirectional-everything diagram. This is the seven-pillar system from `01-overview` section 2, classified consistently with the slide-6 truth table. The moat reframe is counsel-verified (section 12, revision 2): relationships compress the sales cycle, speed compounds client data, the estate is a packaged demonstrable asset. The old slogan form is cut.

## Appendix B: The horizon: marketplace and attribution

**On slide:**
- The skill marketplace is the long-term network effect. Skills and workflows are the commodity. A 296-skill personal registry with a nightly self-improver is the proof of the pattern, not a claim of traction.
- Attribution is proof-of-origination for ideas and work. It's the least-built pillar today. It's on the roadmap, named as designed, not running.

**Speaker notes:**
Gate E: the research corpus and skill registry are INPUTS, never demand validation or traction. Attribution has zero code today; it must not anchor the whitespace claim (counsel item 21, section 12 revision 10). Marketplace is a long-term differentiator, tokenization parked.

## Appendix C: N=1 operating evidence

**On slide:** the appendix label **N=1 operating evidence** is shown on the slide. The reference implementation, measured from live telemetry. One operator, one estate. Not an installed customer.
- Internal agent OS, running org-wide since 2026-07-01.
- OKR engine: scored 99.3% of commits against the objective tree on its first run (275 of 277).
- Achievement engine: 5,027 points, a 23-day streak never broken, live since 2026-04-19.
- Fleet HUD: 322 commits, session recall cut from 8 to 10 seconds down to 0.06.
- Meeting capture: 343 processed notes, 47k embeddings, 5 real tasks from one meeting.
- Skill registry: 296 skills, 835 commits, a nightly self-improver.
- Consultative delivery: 6-plus active clients, one retained at $25,000 a month.

**Speaker notes:**
R6 and B3: all activity and inventory counts live HERE, in the appendix labeled N=1 operating evidence, never in the lead. Every figure is MEASURED from Jarred's own estate telemetry, n=1, reference implementation (gate D), not customer traction (gate E). The $25k/mo client is named nowhere (gate C); "one retained client" is the safe phrasing. Each line answers the proof-pattern question: what changed, or what risk did the system control. No readiness score appears here or anywhere (hard law).

---

## Self-QA checklist (this deliverable)

- [x] No em dashes; no " -- " sequences. Verified by grep.
- [x] No 16x anywhere (R4). No throughput comparison, incl. the retired output-parity line (S1).
- [x] No "3x floor / 10x ceiling" or derived "1%" line (S2).
- [x] No multi-year revenue projections; pilot P&L shape only.
- [x] No model-panel verdict badges (B5).
- [x] No client name; the $25k/mo client is unnamed (gate C).
- [x] Fleet-of-one labeled reference implementation everywhere (gate D).
- [x] Corpus + skill registry framed as inputs, not traction (gate E).
- [x] Canonical ask verbatim, identical to exec overview + one-pager (ADDENDUM 1.1).
- [x] Two-transaction ask early as orientation (R5) + re-landed with R8 two branches.
- [x] Reproducible trace + four-column truth table lead the proof (R6, B4).
- [x] Demo scope read-only, spike truth stated honestly (R3, B2).
- [x] No "brand in stealth"; unnamed-by-design owned (S3). "agent OS" lowercase descriptor only (S4).
- [x] No "co-founder," "three founders," or fixed-split; contribution-earns-equity (correction 5). No Upexi, Mima, Recurro-as-name.
- [x] Every stat lineage-tagged; every list 2-3 items; no em dashes; contractions used (VOICE_SPINE).

## Open items only the founder can answer
1. The pilot fee number and the post-pilot retainer band (both [unverified]; nothing quotable until Jarred + counsel clear the terms skeleton).
2. Which role Allan plays: operating counterparty vs sponsor (R8 precondition; decides which branch is the primary at close).
3. Was the State-of-AI teaching deck actually delivered to Allan (decides whether slide 2 assumes shared vocabulary or teaches from scratch).
4. A real live screen capture of the running front door to drop into slide 8 before send (currently a framed rendering).
