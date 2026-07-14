# The trusted companion through the AI transition

**DRAFT v1 for founder review (gate 1.3). Not for circulation. Render to stylized HTML/PDF only after review.**

**Workstream:** W1 concept doc + deck | **Task:** 1.3 | **Drafted:** 2026-07-08
**What this file is:** the markdown SOURCE for the 7/15 concept document. The client-facing artifact is a stylized HTML/PDF render produced only after founder review; raw markdown never ships (hard law). Counsel securities pass (1.7) and founder sign-off (1.8) precede any send.
**Structure:** the deck skeleton's 16-slide arc (`deck-skeleton.md`) expanded to document depth, one section per slide.
**Ruling order:** CLAUDE.md corrections > decision 0003 > overview section 12 > counsel verdicts > overview body.
**Voice:** written to `recipient-profile-alan.md` (VOICE_SPINE v1.1). Short sentences. Lists capped at 2-3 items; where structure needs more, a table carries it. No jargon, no hype, no forward-looking promises, no "I built" framing.
**Lineage tags, used inline on every stat:** MEASURED (we or a named third party measured it) / SURVEY (published survey) / VENDOR (vendor-published figure, secondhand where noted) / [unverified] (candidate number, not confirmed, not quotable in the room).
**Product naming:** the product is UNNAMED. Every descriptor below ("organizational operating system," "the companion") is a descriptor, never a name.

---

## 1. The category

Every company is about to run on agents. That part isn't in question. The question each CEO actually faces is simpler: who takes us through it without breaking what works.

This document describes a gamified, AI-powered operating system for organizations. One calm surface where anyone, CEO to line worker, directs agent work and consumes the results. It's delivered as consulting plus software, because no box product survives contact with a real org chart.

The product is deliberately unnamed today. The category it occupies has a name: the trusted companion that brings a company through the AI transition and gives it a head start.

Companies won't be sorted by which AI they bought. They'll be sorted by who they trusted to install it.

## 2. Where the market actually is

The noise says everyone is doing this. The measured numbers say almost no one is.

- 62% of organizations are experimenting with AI agents; roughly 6% qualify as high performers (SURVEY, McKinsey).
- 17% have actually deployed (SURVEY, Gartner).
- Roughly 5% capture real value from what they deploy (SURVEY, MIT).

Worked through: 17% deployed x ~5% capturing value lands near 0.85%. Call it 1 in 100 companies operating on agents in any real sense (derived from the SURVEY figures above; the derivation stays attached to the number wherever it appears). We take the smaller, sourced number every time. That discipline held once before in material prepared for this recipient, when an 88% adoption headline was walked back to the ~1% it really supported.

This isn't a fear window and we put no clock on it. It's an early-mover fact: being early here compounds, being on time doesn't.

## 3. The premise: the frontier labs can build this

Let's say the uncomfortable part ourselves. Anthropic and its peers can build everything described in this document. That's not a risk to this plan. It's the premise of the market.

Frontier capability is why the transition is happening at all. But capability doesn't install itself. A company needs someone who knows its people, its meetings, its objectives, and its risk lines, and who stays accountable while the org changes underneath. That's a companion role, not a platform feature.

We keep ordinary engineering hygiene underneath: the system can swap the model vendor it runs on, and every account and key is audited (counsel-kept, 4/4). One line, because that's what it is: hygiene, not a fear posture.

The labs supply the engine. Somebody still has to drive the org through the mountain pass. That second job is the business.

## 4. What it is

One conversational surface for the whole company. You talk to it the way you text a colleague. Behind that surface, three things happen.

1. Company objectives get decomposed into weighted subtasks that agents execute, so every piece of agent work scores against a stated objective.
2. Game mechanics reward the people who adopt, instead of threatening them with replacement.
3. A human gate sits in front of anything that touches money, anything irreversible, and anything external. Always.

The single KPI the whole system optimizes: "the compression of time between thought and output" (MEASURED, call verbatim, 2026-07-08). The adoption contract, also verbatim: "we're not doing this so you can replace your employees, we're doing this so you can reward your employees and retain them" (MEASURED, call verbatim, 2026-07-08).

Most AI rollouts fail on people, not technology. This one is built people-first on purpose.

## 5. One system, seven pillars

These aren't seven products. They stack into one, and the stack is the point. (A table carries the seven; no slide list exceeds three items.)

| Pillar | Role | One line |
|---|---|---|
| Conversational surface | The face | One front door: a conversation pane plus a workspace pane. Approve, edit, or skip. Noise stays out; facts, questions, and decisions come through. |
| Objective engine | The brain | North Star, then drivers, then key results, then weighted agent-run subtasks. Every run scores against a stated objective. |
| Game mechanics | The adoption engine | Points, tiers, streaks, leagues. Decoupled from compensation, with anti-abuse on from day one. |
| Meeting capture | The senses | Meetings become transcripts, decisions, actions, and memory while people are still in the room. |
| Client delivery | The channel | Consultative engagement is how the software lands inside a company and stays. Part of the product, not overhead. |
| Skill marketplace | The network effect | Skills and workflows become the commodity; a working 296-skill internal registry is the proof of pattern (MEASURED). Long-term; tokenization parked. |
| Attribution | The trust layer | Proof of who originated, who authorized, what ran on its own. Roadmap-stage; nothing built yet, and we say so. It supports the story here; it doesn't carry it. |

Any one pillar can be copied. The stack, delivered by a companion who's accountable for the whole, is the thing nobody currently sells.

## 6. The dominos: how it enters a company

The entry order is confirmed and simple.

1. C-levels first. A chief-of-staff seat for the executive: their meetings, their follow-through, their one gated workflow.
2. Engineers next. A department revamp informed by Recurro, Carter Razink's framework for agentic engineering (his framework, feeding this pillar; not this product's name).
3. Everyone else follows on demand, packaged good, better, best.

Why this order works: the executive seat produces evidence on the CEO's own calendar, and engineers turn that evidence into internal pull. Demand walks down the org chart on its own. Nobody has to push it.

## 7. The running system

This concept isn't a plan on paper. A reference implementation runs today at fleet-of-one scale, and it's inspectable live.

What runs now, all MEASURED on the reference implementation (n=1, one operator's estate; we say that plainly):

- An internal agent operating system enforced org-wide since 2026-07-01, plus an always-on fleet dashboard (322 commits, the estate's most active repo).
- An objective engine scoring real work against stated objectives: 99.3% alignment on its first run across 275 of 277 commits.
- An achievement engine live since April with an unbroken 23-day streak; a meeting pipeline that has processed 343 meeting notes into decisions, tasks, and memory; a 296-skill registry that improves itself nightly; and a consulting delivery machine with paying clients, including a signed $25K/mo retainer (MEASURED).

The demonstration precedent already exists for this recipient: four live, clickable demo pages built against real operational pain, fleet registration and treasury visibility among them. The same rule applies to this document. Nothing here is a mockup of intent; it's a photograph of an operation.

One is a small number and we won't pretend otherwise. But one running system beats any number of decks, and this is the only one like it we know of that's running.

## 8. The adoption engine: reward, not replace

Every employee has heard the quiet threat inside "AI transformation." This system inverts it. Adoption earns points, tiers, standing, and time back. The verbatim contract from section 4 is the design brief.

Three design rules keep it honest.

1. Game mechanics stay decoupled from compensation (counsel-kept, 4/4). Recognition and time first; money mechanics only later, deliberately, with HR at the table.
2. Anti-abuse is on from day one: caps, outlier detection, role-adjusted scoring. Nick Metzler, originating member and the game designer here, has watched his own published metric get gamed by professionals; the mechanics assume adversaries.
3. Output and value get measured, never hours or activity.

Status, honestly tagged: the single-operator version runs today (MEASURED, section 7). The multi-person mechanics are design-stage; Nick's mechanics definition lands 7/31. Nothing here claims a shipped multi-player system.

Gamification has a documented backlash history when it's done as surveillance with points. Done as reward with consent, it's the difference between a rollout people endure and one they ask for.

## 9. Product law: how trust is earned

The panel of four independent reviewers that examined this concept called this section the best-specified item in it, verdict: "don't touch it." So we haven't.

- No agent ever acts on money, anything irreversible, or anything external without a human gate. No fee or tier purchases an exception, ever.
- The system fails open to surfacing: decisions, money, deadlines, and irreversible items can never be silently suppressed.
- Autonomy is earned per decision class, never assumed: an agent graduates only after matching the human's actual choice 90% of the time across 20 or more repetitions, with executive sign-off.

Read that as what it is: risk-reduction structure. Gates, a written kill criterion, and a graduation bar do for agent work what covenants do for capital. They cap the downside before anyone discusses the upside.

Every vendor says "human in the loop." Almost none can show you the graduation ledger. We can, and that's an auditable difference, not a slogan.

## 10. Evidence [CONDITIONAL SECTION: resolves on W6, Carter methodology memo due 7/15]

> RENDER RULE: exactly one of the two versions below ships. The PRIMARY version enters only if Carter Razink's methodology memo lands and clears review by 7/15. Otherwise the FALLBACK ships. The fallback is not a lesser claim; it's the same fact stated at the strength the evidence supports today.

**PRIMARY (only with the landed methodology memo):** a 4-engineer team measured at 16x baseline output against an 18-engineer control team at 2.5x, with the methodology, measurement window, and definitions attached (tagged per the memo when it lands; [unverified] until then).

**FALLBACK (default, ships unless W6 clears):** output parity. A team of 4 matched the output of a team of 18 ([unverified], Carter Razink's engagement observation; methodology in preparation). We won't put a multiplier on it until the measurement is on paper.

What's sourced today, independent of that case:

- A randomized controlled trial found roughly 40% quality improvement on knowledge-work tasks with AI assistance (MEASURED, BCG RCT; source in the deck research packets).
- Loop deletion, not speed-up, is where the money is: review cycles compressed from 13 rounds to 1, and 24 days to 5, in the documented cases carried in the same packets (MEASURED per packet sources).

The honest frame for all of it: don't buy a multiplier. Count the loops that stop consuming your people. Deleted loops are auditable; multipliers usually aren't.

## 11. What it's worth, seat by seat

**To the employee.** AI that pays you, in the currencies that matter: recognition, standing, and time back. Output buys hours off, not a layoff list.

**To the C-suite.** One window of consequence. In the built demonstration scenario, a full day of delegated agent work resolved into 14 actions, 3 approvals, and 41 seconds of executive attention (MEASURED as a built demo scenario, not a client result; it becomes a client-measured number only inside a pilot). And objectives finally wired to execution: every agent-run subtask scores against the objective tree.

**To the organization.** Compression of thought-to-output as the economic lever. The sourced band we'll stand behind: a 3x floor with a 10x ceiling on affected workflows (SURVEY/MEASURED mix, carried with sources in the deck research packets), told through deleted loops per section 10, never through raw multipliers.

Worked example of the honest-math rule in practice: we don't dollarize an executive's recovered hours at some asserted market rate. The buyer names their own rate at kickoff, or the hours get reported raw. If the pilot recovers 3-6 hours a week (MEASURED band, n=1 reference implementation; generalization [unverified]), 13 weeks makes that 39-78 hours; the buyer's own number prices it. Their arithmetic, not ours.

Value claims that survive the buyer's own auditor are the only ones worth making.

## 12. The open ground, and the honest threat read (one page, together)

These two facts are true at once, and they belong on the same page.

**The open ground.** No funded company today occupies the specific stack this document describes: objective-scored agent execution, plus adoption game mechanics, plus attribution, delivered as a companion engagement ([unverified] as an absence-of-evidence claim; a monthly competitive review sustains it or retires it). We put no time window on this. Any number of months would be false precision, so we don't say one.

**The threat read.** Two of the seven pillars are commoditizing fast right now: meeting capture and agent chat surfaces (per the competitive dossiers in this corpus). Anyone building on those two pillars alone is building on sand, and we'd say so about our own plan if it did.

The reconciliation is the strategy itself. The defensible position was never any single pillar. It's the un-commoditized combination, scored objectives plus consented game mechanics plus earned autonomy, installed and operated by a companion who's accountable for the whole. Attribution supports this claim as a roadmap-stage pillar; it doesn't anchor it, because nothing of it is built yet and we don't lean on unbuilt things.

Whitespace claims usually die under one good question. This one is stated with its own counterargument attached, which is why it can survive the room.

## 13. Competitors, named

We name them ourselves, because self-disclosure beats discovery, and because a plan that can't say its competitors' names out loud isn't a plan.

The one move already carrying a source in this corpus:

- Cognition (Devin) sells engineering outcomes at scale: a $1B+ Series D at a $26B post-money valuation (MEASURED, TechCrunch + Cognition's own announcement, 2026-05-27) on a reported $492M ARR run-rate (VENDOR, company-disclosed, not audited; primary sources in `competitor-sources.md`). It validates that buyers pay for outcomes, and it sharpens the engineering domino rather than blocking it.

> **[SOURCES CLEARED 2026-07-08 with residue] - see `competitor-sources.md` (this folder) for every claim, URL, publisher, date, and lineage tag.** All items in the original pending list cleared the primary-or-strong-secondary bar and may render with their tags attached: Microsoft (Agent 365 GA 2026-05-01; Viva Goals retired 2025-12-31 with no replacement), Salesforce (Agentforce $800M ARR / 29,000 deals, Q4 FY26 earnings release, VENDOR tag mandatory), ClickUp (Super Agents + Brain²), the meeting-capture field (Otter consolidated wiretap litigation, Zoom AI Companion 3.0, Granola $125M Series C), OKR incumbents (WorkBoard/Quantive plus its shipped "AI Chief of Staff" agent), and the documented gamification-backlash precedent (Meta's internal token leaderboard, shut down after press exposure, Fortune 2026-04-09) presented alongside our decoupled-from-comp answer. **Still render-blocked** (do-not-render list in `competitor-sources.md` section 2): Lattice AI Leverage Insights, Amazon "KiroRank" specifics, Otter user counts, Uber/Tesla budget-cap figures, Anthropic Cowork timeline specifics, and any Slack/Notion/Linear/Atlassian move; none of these renders until a later monthly review sources them. Cadence owner: monthly competitive review (W10 task 10.4, next review 2026-08-08).

The bar for this section is simple: every named move carries a source a skeptic can click. What can't meet that bar doesn't get said.

## 14. Business model

Consulting plus software, in that order, on purpose.

- Consulting revenue leads. It funds the build and generates evidence at the same time (counsel-kept, 4/4). The precedent is signed: a $25K/mo retainer on the existing book (MEASURED). The product itself has no revenue yet; we say that plainly.
- Equity plus cash is the default on transformative engagements; cash-only requires explicit partner sign-off. We want to be aligned with the outcome, not just paid for the attempt.
- The skill marketplace is the long-term network effect. Tokenization is parked; it would detract right now.

What the advantage actually is, in diligence-grade terms rather than slogans: relationships compress sales cycles; delivery speed compounds client data; and the running reference implementation is a packaged, demonstrable asset no competitor can photograph.

On the people behind it: Jarred Winn is the founder; the vision and the operating estate are his. Nick Metzler (game design, adoption mechanics) and Carter Razink (engineering, his Recurro framework) are originating members who earn equity through contribution. Entity formation and IP assignment are in motion this week.

A business model where the operator eats the same risk as the client is rare in consulting and rarer in software. That alignment is the product working on its own P&L.

## 15. The 90-day design-partner pilot

Ninety days, two phases, instrumented before day 1. The structure is the offer; every threshold number below is a candidate the partner co-signs, not a term we impose.

**Before day 1: the baseline gets signed.** A two-week executive time audit (B1), a day-0 count of open follow-up commitments (B2), a named business owner, a written kill criterion, and a dollarization rule: the buyer's own rate or raw hours (all baseline mechanics per the pilot design; the 3-6 hours/week reference band is MEASURED n=1; its generalization is [unverified] until the audit).

**Days 1-30: capture plus one gated workflow.** Meeting capture live on a designated, disclosed surface; one workflow, selected together in week 1, running in production behind human gates. Day-30 gate: 90%+ capture coverage [unverified candidate], 15+ gated executions [unverified candidate], and zero ungated actions, which is a hard requirement, not a candidate.

**Days 31-90: game mechanics for an opt-in cohort.** Entering only on day-30 evidence, anti-abuse on from its first day. Day-60 and day-90 gates measure participation (60%+ weekly active [unverified candidate]), executive hours recovered against the signed baseline, follow-up debt reduction (50%+ [unverified candidate]), and graduation progress on the gated decision class.

If the kill criterion trips, the pilot stops and we say so in writing. A pilot that can't fail can't prove anything either.

No fee appears in this section or in the meeting room until counsel and founder clear the terms (working band exists internally, [unverified], founder sets it). The structure above is quotable today; the numbers aren't.

## 16. The ask, and the three ways this can go

The ask is scoped to the evidence, deliberately: a 90-day design-partner pilot, plus a smaller strategic check, papered separately and never blended. This is not a raise. The raise conversation happens later, on evidence, with the pilot's measured results on the table.

Why this shape and not a bigger one: staged, priced-by-proof capital is the discipline the recipient already practices. A large diffuse ask at this evidence level would deserve to be declined. A scoped pilot with signed baselines, 30/60/90 gates, and a written kill criterion is capital deployed the way an operator deploys it.

Both seats are on the table. The pilot is the operator seat: hands on the system, evidence on your own calendar. The check is the owner seat: an early position at the lowest base this will ever have, taken from strength, sized by counsel and founder off-slide. This is a shift to own a stake in, not merely to use.

The three branches, each an acceptable outcome we name out loud, are carried in full in the companion section (`branch-scenarios-section.md`, task 1.4; it drops into this document here at render time, including the worked hurdle calculation).

On the people and the paper, one more time for the record: Jarred Winn is the founder. Nick Metzler and Carter Razink are originating members earning equity through contribution. Entity formation and IP assignment are in flight this week, and the written conflict-of-interest disclosure executes before any money moves.

The whole document reduces to one arguable sentence: the evidence shown here justifies exactly the ask being made, no more, and an ask that matches its evidence is the rarest thing an investor gets shown.

---

## Draft-level render notes (strip before render)

1. **Section 10 fork** resolves on W6 (Carter methodology memo by 7/15). Exactly one version renders.
2. **Section 13 sourcing** cleared 2026-07-08 via `competitor-sources.md`; the policy stands (no named move renders without a source), and the do-not-render residue list in that file stays out of every rendered version.
3. **Section 16 merge:** `branch-scenarios-section.md` drops in as the branch detail; the worked hurdle calculation appears once in the rendered document (in the merged branch section, not duplicated).
4. **Fee band and all threshold numbers** stay [unverified] and off the rendered pages until founder + counsel clear the terms skeleton.
5. **Counsel securities pass (1.7)** covers this document, the branch section, and all presenter notes before 7/17; founder sign-off (1.8) precedes render.
6. **Open recipient items that may re-index sections 2-4:** whether the State-of-AI deck was delivered and how it landed; the postponed prep call outcome.
