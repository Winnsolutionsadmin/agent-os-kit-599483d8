# Exec-overview extract notes — raw material for the author

**Compiled:** 2026-07-09. **Method:** full read of `01-overview/product-concept-overview-2026-07-08.md` (incl. section 12 counsel deltas) + `05-counsel/counsel-deepdive-2026-07-09.md` + `05-counsel/counsel-deepdive-opus-2026-07-09.md`; targeted reads of `memory-bank/decisions/0003-founder-structure-funding-positioning.md`, `memory-bank/activeContext.md`, `07-roadmap/ROADMAP.md`, `09-deliverables/founder-memo/_extract-notes.md`; rg sweep of the corpus for proof-point numbers, honest-math stats, and the exec-overview-specific brief. Quotes below are verbatim — do not paraphrase them; cite the file path when you use one.

**Do not do this:** the source overview names Upexi explicitly in its own section 7/8 ("Upexi active, separate Winn.solutions engagement, unrelated to this initiative") because that document predates/documents the correction inline. **The exec overview must never repeat that name.** Where you cite "two paying clients" or the consultative delivery machine as a proof point, cite Anchorage ($25k/mo, named explicitly below) and describe the second only as a second retained client, never named. This is the single highest-risk copy-forward defect for this deliverable.

**Independent re-verification pass (2026-07-09, second extraction run):** every cited quote below was re-checked against source on this pass with zero discrepancies: `01-overview/product-concept-overview-2026-07-08.md` (lines 11, 13, 15, 17, 19, 35, 37, 43-51, 59, 122, 163, 202, 250, 271, 274, 276), `memory-bank/decisions/0003-founder-structure-funding-positioning.md` (lines 6, 8-10), `05-counsel/counsel-deepdive-2026-07-09.md` (lines 4-6, 39, 73), `05-counsel/counsel-deepdive-opus-2026-07-09.md` (lines 60-65), `03-execution/gamification-evidence.md:22`, `03-execution/pilot-design.md:23`, `03-execution/case-study-hardening.md:38`, `04-competitive/redteam-plan.md:29`, `07-roadmap/ROADMAP.md` (lines 25, 32-38), and `06-deck-inputs/README.md` (confirms gap #7: no domino-ladder or front-door graphic on file, pointers only). No stale claims found; CLAUDE.md corrections, decision 0003, and section 12 deltas are all internally consistent as of this pass. Nothing below needed correction; treat this file as ready for the author.

---

## 0. The brief for THIS deliverable (what counsel actually asked for)

Two independent panelists graded the exec-overview deliverable specifically:

> "Exec overview: high signal-to-noise; clear problem/solution; explicit domino GTM; visual human-gate triage. Failure: cramming the 30KB doc into 3 pages instead of aggressive editorial synthesis."
— gemini, `05-counsel/counsel-deepdive-2026-07-09.md:39` (distilled directives) and `:73` (raw, item d)

> "(d) Digestible 2 to 3 page executive concept overview — Ruthlessly compress: what it is, why now, the seven pillars in one line each, the domino GTM, the ask. Nothing that needs a footnote. Written for a C-level reader in five minutes, one strong visual (the front door or the domino ladder), plain language, no jargon. Carries the same canonical ask and the same honest-math discipline as the deck, and survives being forwarded without Jarred in the room. End on a concrete next step (the pilot shape), not a vision flourish. **Most common failure mode:** it becomes a compressed everything and loses the single takeaway, so the reader finishes unable to say in one sentence what the company is."
— opus 4.8, `05-counsel/counsel-deepdive-opus-2026-07-09.md:60-65`

Binding cross-artifact rule (opus addendum, applies to every deliverable including this one):
> "ONE CANONICAL ASK, verbatim everywhere: 'A scoped 90-day design-partner pilot plus a smaller strategic check. The larger raise comes at roughly month 6, triggered by demonstrated achievement.' Every artifact that states an ask uses this exact framing; incoherence across artifacts is fatal to conviction capital."
> "BUILT-VS-DESIGNED LINE, hard rule: nothing designed-but-unbuilt may speak in the present tense. Built things are named as running; designed things are named as designed."
— `05-counsel/counsel-deepdive-2026-07-09.md:4-6`

---

## 1. The problem / why now

**Core KPI (verbatim, use this as the opening frame):**
> "The compression of time between thought and output - that's the main KPI we're optimizing for."
— `01-overview/product-concept-overview-2026-07-08.md:13`

**Urgency thesis (Carter, verbatim):**
> "Everybody in the next six, nine, twelve months are going to have an operating system product for their business. The question is who's gonna be the first one."
> "The first org to do this with the fastest exponential will monopolize a vertical - we can't take cash alone, we need equity."
— `01-overview/product-concept-overview-2026-07-08.md:17`

**Adoption fear is the real blocker, not capability (this IS the problem statement):** employees hide AI use because disclosure carries a social penalty, which is the opposite of what any adoption-dependent product needs. This is the empirical case for reward-not-replace as strategy, not just ethics.
> "The disclosure penalty (Atlassian research, 2026): 94% of US knowledge workers report using AI at work, but in a controlled experiment, a peer who disclosed AI use was rated 10x lazier and was 24 percentage points less likely to be recommended for a high-visibility project, with identical output, versus a peer who did not disclose."
— `03-execution/gamification-evidence.md:22` [SURVEY/VENDOR — Atlassian, 2026, controlled experiment; cite as: SURVEY]

**Base-rate whitespace (early-mover math — use with tags, do not round to "1%" without the tag lineage):**
- McKinsey: 62% of orgs experimenting with agents, only ~6% classed as high performers — SURVEY
- Gartner: 17% already deployed — VENDOR
- MIT: ~5% of value captured realized economy-wide — SURVEY
— all three cited together at `01-overview/product-concept-overview-2026-07-08.md:202` and `02-sweep/swarm-gui.md:84`

**Pilots fail at scale today (use to justify why a *design-partner pilot*, not a generic rollout, is the right ask — but flag the contested methodology if quoting the headline number):**
> "MIT's NANDA-affiliated 'GenAI Divide: State of AI in Business 2025' report... found about 95 percent of generative AI pilots fail to reach measurable P&L impact within six months, and that externally-built or vendor-partnered tools succeed roughly twice as often as internal builds (about 67 percent versus one-third)."
— `03-execution/pilot-design.md:23` [CORPUS/VENDOR — methodology publicly contested by Marketing AI Institute; the "zero return" finding rests on only 52 interviews. Treat directionally, cite the caveat if used.]

**The category is open (this is the actual "why now," per decision 0003 — see section 4 below for the full quote):** frontier labs can build the underlying capability; nobody has claimed the trusted-companion/adoption layer yet.

---

## 2. The product in one paragraph

Use section 1 of the overview near-verbatim (already tight):

> "A gamified, AI-powered operating system for organizations: one calm conversational surface through which any employee, from CEO to line worker, directs and consumes agent work; org-level OKRs decomposed into weighted, agent-executed subtasks; adoption driven by game mechanics that reward people for using AI instead of threatening them with replacement; delivered as a consulting + software hybrid that takes cash + equity."
— `01-overview/product-concept-overview-2026-07-08.md:11`

Adoption thesis to pair with it (verbatim, this is the emotional hook counsel keeps calling out as the thing that must not get lost):
> "We're not doing this so you can replace your employees, we're doing this so you can reward your employees and retain them based on the fact that they are then going to be adopting AI."
— `01-overview/product-concept-overview-2026-07-08.md:15` (also the founder's own first-person phrasing, `00-call-notes/2026-07-08-jarred-nick-carter-ai-productivity-os-gamification-ideation-9f36bc52.md:75`, reproduced in `09-deliverables/founder-memo/_extract-notes.md`)

The category line (repeat verbatim per decision 0003 / hard rule 7 — a reader should be able to repeat this sentence back):
> "Companies need trusted companions to bring them through this and help them get a headstart."
— `memory-bank/decisions/0003-founder-structure-funding-positioning.md:6`

The unfair-advantage line (why THIS founder, why now — pairs well with the proof points in section 5):
> "Jarred already runs the reference implementation. His own estate IS the product at fleet-of-one scale... 'This deck is the demonstration' generalizes to: this operation is the demonstration."
— `01-overview/product-concept-overview-2026-07-08.md:19`

---

## 3. The seven pillars (one line each, per the brief)

Source list (compress further for the deliverable; this is the fullest verbatim version to cut down from), `01-overview/product-concept-overview-2026-07-08.md:27-33`:

1. **GUI is the face** — one "front door": conversation pane + workspace pane, intent bar (Ask / Save as idea / Convert to task / Save as workflow / Build it now), Approve/Edit/Skip triage cards. Suppress noise; surface only facts, questions, decisions.
2. **OKR engine is the brain** — North Star → Drivers → Key Results → weighted agent-run subtasks. Every run, commit, task scores against a stated objective.
3. **Gamification is the adoption engine** — points, tiers, streaks, leagues, role-adjusted scoring, anti-abuse caps, rewards economy. Reward-not-replace, decoupled from comp on day one.
4. **Meeting capture is the sensory layer** — transcripts → CRM, action items, decisions, memory. "Nobody takes notes. Nobody recaps... everything it decides gets built while you are still in the room."
5. **Client relationships are the delivery channel and part of the moat** — counsel-verified reframe (do NOT use the original slogan): relationships = sales-cycle compression; speed = client-data compounding; the fleet-of-one estate = a packaged, demonstrable proof asset. ("Moat: trust, relationships, speed — nothing stops Salesforce/ClickUp from copying" is the ORIGINAL call framing and does **not** survive diligence per counsel; do not use it as the pillar statement, use the reframe.)
6. **Skill marketplace is the network effect** — "Skills and workflows are going to be the commodity." 296-skill personal registry with a nightly self-improver is the proof-of-pattern. Long-term differentiator, not a pilot claim.
7. **Attribution is the trust layer** — proof-of-origination for ideas and work. Currently the least-built pillar (zero code, zero docs) — roadmap item, not a claim of present capability.

Packaging line (good/better/best, pairs with dominos below):
> "Sell the C-levels first. Then engineering. Then the whole org."
— `01-overview/product-concept-overview-2026-07-08.md:35`

Delivery-model line (why consulting is part of the product, not overhead):
> "This isn't an in-the-box solution - it's an in-the-box solution that requires out-of-box consultation per business."
— `01-overview/product-concept-overview-2026-07-08.md:37`

---

## 4. Dominos (GTM ladder) — visual candidate #2 per the brief

**The canonical verbatim (decision 0003, use this whole block or the ladder line alone):**
> "Dominos fall as
> C-levels first - chief of staff/organizer
> Engineers next - revamp/overhaul
> All else follows based on demand."
— `memory-bank/decisions/0003-founder-structure-funding-positioning.md:8-10`, restated identically at `CLAUDE.md` item 8 and `07-roadmap/ROADMAP.md:3`

**Caution baked into hard rule 8 language:** dominos are a **GTM motion**, not an ICP — do not let the exec overview imply "C-level chief of staff" alone defines the buyer; that's a known blind spot (see GAPS). Gemini's phrasing: "'C-levels first' is a GTM motion, not an ICP; define the first-10-customers target precisely" (`05-counsel/counsel-deepdive-2026-07-09.md:64`) — no such precise ICP exists yet in this corpus (blind spot #1, unresolved).

**"First hit" framing (Jarred, verbatim — useful color for why C-suite-first works as a wedge):**
> "I never leave my Claude code terminal anymore... getting it to a level that people can see like what's possible. Like that's kind of like my first thing that I'm giving Alan is like his first hit, so to speak."
— `00-call-notes/2026-07-08-jarred-nick-carter-ai-productivity-os-gamification-ideation-9f36bc52.md:69`, also `01-overview` section 8 GTM-ladder gloss: "The first one's free - classic addiction strategy."

---

## 5. Proof points (the estate-is-the-demonstration evidence)

**Frame line:** "This operation is the demonstration" (see section 2 above). Everything below is BUILT and RUNNING — safe to state in present tense per the built-vs-designed hard rule. Do not blend in Tier B/C/D items (prototypes, specced-only, meeting-stage) without explicitly flagging them as designed, not running.

Tier A (shipping, internal, fleet-of-one), `01-overview/product-concept-overview-2026-07-08.md:43-51` — pull only the numbers you need, all MEASURED (internal telemetry, Jarred's own estate):
- Internal agent OS shipped org-wide 2026-07-01 (doctrine injection, closeout gates, nightly sweeps, memory tiering) — MEASURED
- **claudecode-bar**: 322 commits (most-active repo in the estate), always-on fleet HUD, 103-component estate dashboard, click-to-debug session spawning, 2-step-confirm Approvals panel, session-search recall (8-10s → 0.06s) — MEASURED
- **the-sage** (OKR engine): `score_alignment()` scored 99.3% of 275/277 commits against the objective tree on its first run — MEASURED
- **Achievement engine**: live since 2026-04-19; today's tally 5,027 points, 23-day streak never broken; scored the founding 7/8 meeting in near-real-time — MEASURED
- **Meeting-capture stack**: 343 processed notes / 47k embeddings, 3-tier auto-classification; fieldy-to-ClickUp extraction armed in shadow mode (5 real tasks pulled from one meeting) — MEASURED
- **Skill registry**: 296 skills, 835 commits, nightly self-improver — MEASURED
- **Consultative delivery machine**: 6+ active clients scaffolded (67 archived), client-feedback registries mechanically gating content, 7 per-client style guides; **Anchorage $25k/mo signed** (name this one only; do not name the second client) — MEASURED

**Live demo pages** (published, unlisted — the four watch-it-happen assets, safe to name as running):
> treasury.html (agentic treasury desk), fleet.html (20-vehicle registration agent with dollar approval cards + "your time YTD"), triage.html (front-door pattern), imessage.html (full day run by text: "14 actions, 3 approvals, 41 seconds of attention").
— `01-overview/product-concept-overview-2026-07-08.md:59`, live at winnsolutionsadmin.github.io/allan-ai-demos/ — CORPUS (internal build, not yet independently benchmarked)

**Readiness-score framing (internal only — hard law: NEVER on a slide/in a client-facing artifact, but useful to the author privately):** P0 feature-strength average 3.6/5 today; two moves (case-study hardening + one live front-door demo) lift it to ~4.1/5 pre-pitch. `01-overview/product-concept-overview-2026-07-08.md:122`. **Do not put this number, or any readiness score, in the exec overview itself** — it is explicitly internal-only per counsel and per CLAUDE.md hard law.

**The one thing NOT yet built that the pitch leans on:** a single live, real front-door demo (the exec-agent-gui "answer-relay spike") does not exist yet — the four demos above are the current fallback. Opus: "Package one live, watch-it-happen front-door demo from the estate... Make it literally visible in the room." (`05-counsel/counsel-deepdive-opus-2026-07-09.md:16`). If the exec overview is written before the spike lands, describe the four published demos as running (they are) and the answer-relay spike as in-progress/roadmap, not as delivered.

---

## 6. The pilot ask (near dates + canonical framing)

**Use this sentence verbatim, this deliverable's ask must match every other artifact word-for-word:**
> "A scoped 90-day design-partner pilot plus a smaller strategic check. The larger raise comes at roughly month 6, triggered by demonstrated achievement."
— `05-counsel/counsel-deepdive-2026-07-09.md:5` (opus addendum, binding)

**Pilot phasing (counsel-kept, unanimous 4/4 panel 2026-07-08):**
> "Pilot phasing (capture + one gated workflow days 1-30, gamification 31-90)."
— `01-overview/product-concept-overview-2026-07-08.md:271` (section 12, kept-unanimously list)
Roadmap restates identically: "90-day design-partner pilot plan: days 1-30 capture + one gated workflow, 31-90 gamification." — `07-roadmap/ROADMAP.md:25`

**Why NOT the big number (the single most load-bearing correction in the whole repo — sourced directly, use this reasoning in the exec overview's ask framing):**
> "The ask (strongest consensus; 'the organizing principle'): 7/17-18 is a scoped 90-day design-partner pilot + smaller strategic check, NOT a $10-50M raise. Current evidence (one unhardened case study, no entity, single-founder estate) does not yet earn the big ask; the ask should be sized to what is earned by demonstrated achievement and put to investors already in relationship, not sized to satisfy a stranger's audit."
— `01-overview/product-concept-overview-2026-07-08.md:274` (section 12, delta 1)

**Funding-model framing (verbatim, decision 0003 — the "why this ask, why these investors" line):**
> "We would raise funding based on achievement and faith from investors we know already."
— `memory-bank/decisions/0003-founder-structure-funding-positioning.md:6`

**"Never cash alone" (softened per counsel — use if the ask section mentions structure):** equity + cash is the default on transformative engagements; cash-only requires partner sign-off. `01-overview/product-concept-overview-2026-07-08.md:276` (section 12, delta 3).

**Entity caveat (say this plainly if the exec overview touches structure at all — do not skip it):** entity formation + IP assignment + contribution-earns-equity framework for Nick/Carter is due THIS WEEK and is counsel-flagged as survival-critical/fatal-flaw-if-missing; no artifact should imply a check can be taken before that lands. `CLAUDE.md` live-commitments table; `memory-bank/activeContext.md:14`.

---

## 7. Near dates (timeline — build a simple table or strip, not prose)

| Date | Owner | Item | Status as of today (7/9) |
|------|-------|------|------|
| 7/9 (today) | Carter | matrix.build GUI-inspiration link | due today |
| 7/10 | Carter | Recurro doc (his agentic-engineering framework) | upcoming |
| 7/9-19 | Jarred (client) | Anchorage Sprint 1 live — capacity collision with the launch-kit window | in progress, flagged risk |
| 7/11 | Jarred | Shared 3-way collaboration doc (Nick/Carter contribution-equity scaffolding) | upcoming |
| this week | Jarred | Entity formation + IP assignment + contribution-earns-equity framework | counsel: survival-critical, not yet done |
| 7/15 | Jarred | Concept doc + early deck with branch scenarios (this repo is the raw material) | upcoming |
| 7/15 | Carter | Packaged 16x case study with methodology | upcoming, not yet landed |
| 7/17-18 | Jarred | Alan/Allan Marshall pitch meeting — design-partner pilot ask | upcoming |
| Days 1-30 post-commit | — | Pilot phase 1: capture + one gated workflow | future |
| Days 31-90 | — | Gamification enters pilot | future |
| 7/31 | Nick | Gamification mechanics definition | upcoming |
| ~Month 6 | — | Achievement-triggered syndicate raise from known investors | future, conditional on pilot evidence |

Source: `memory-bank/CLAUDE.md` (repo root) live-commitments table; `01-overview/product-concept-overview-2026-07-08.md` section 9; `07-roadmap/ROADMAP.md` dependency spine (`:32-38`).

---

## 8. Honest-math tags — apply these exact tags per THIS deliverable's taxonomy (MEASURED/SURVEY/VENDOR/CORPUS/ASSUMPTION)

| Stat | Tag | Note |
|---|---|---|
| 5,027 points / 23-day streak / 99.3% on 275/277 commits / 322 commits / 296 skills, 835 commits / 343 notes, 47k embeddings | MEASURED | Internal estate telemetry, Jarred's own systems |
| Anchorage $25k/mo | MEASURED | Signed, named client (safe to name) |
| McKinsey 62% experimenting / ~6% high performers | SURVEY | External published research |
| Gartner 17% deployed | VENDOR | External published research |
| MIT ~5% value captured | SURVEY | External published research |
| MIT NANDA 95% pilot failure | CORPUS | Contested methodology (Marketing AI Institute critique); cite the caveat if used at all |
| Atlassian disclosure penalty (94% use AI; 10x lazier; -24pp) | SURVEY | Controlled experiment, 2026 |
| RCT productivity 15-40% task-level (Dell'Acqua/BCG, Noy & Zhang/MIT, Cui et al/Microsoft-Accenture) | VENDOR | Published RCTs, use as the honest range, never as the headline multiplier |
| Firm-level 5-15% (DX 2026, 400+ orgs) | VENDOR | "10 percent, not 10x" |
| Anthropic Rakuten case study: 24 days -> 5 days (79% reduction) | VENDOR | Anthropic's own 2026 report; likely direct source of the estate's own "24->5 days" loop-deletion stat — `03-execution/case-study-hardening.md:38` |
| BCG 40% RCT / 13 rounds -> 1 | VENDOR | Cited in `01-overview` section 7/8; verify exact BCG source before deck use per counsel item 12 |
| 16x case study (4 eng @16x vs 18 @2.5x) | ASSUMPTION (until 7/15) | **Never a customer promise.** Internal benchmark via Carter's Recurro framework; methodology memo pending. Overclaim gate exact language below. |
| Output-parity fallback: "4 matched the output of 18" | CORPUS | Prebuilt fallback if the 16x methodology memo slips; use this framing, not a bare multiplier |
| METR 2025 RCT: developers 19% SLOWER with AI on real repo work | VENDOR | Exists in the corpus as a contradicting data point a sophisticated reader may raise — `04-competitive/redteam-plan.md:29`; know it, do not need to cite it, but do not contradict it if pressed |
| P0 readiness score 3.6 -> 4.1 | CORPUS, internal only | **Never on a slide or in any external-facing artifact** — hard law |

**Overclaim gates (exact language to hold this deliverable to, per your task brief and the corpus):**
- 16x = internal benchmark via Carter's Recurro framework with methodology memo pending, never a customer promise.
- Autonomy = the system orchestrates and humans hold the final gate (Approve/Edit/Skip, graduated autonomy 90% agreement over 20+ reps).
- Promise traceability and provenance, never zero hallucination or perfect accuracy.
- Integration honesty: the consultative companion is the bridge, not magic.
- Never claim frontier-lab immunity — concede the capability baseline; the moat is adoption psychology and trust.

Graduated-autonomy exact source (for the human-gate visual the brief calls for):
> "An advisor must match Jarred's actual choice >=90% over >=20 reps before earning auto-act on that decision class."
— `01-overview/product-concept-overview-2026-07-08.md:54` (command-center Tier B note)

---

## 9. Naming placeholder guidance (brief mention only — full brand work is a separate deliverable)

- Product/company is UNNAMED. Use the bracket wordmark "[NAME]" throughout, styled as a deliberate motif (being-named is part of the story), never a real name.
- Ruled-out names (do not resurrect): FleetView, TeamClaude GUI, gui-relay, mission control. Recurro is explicitly off the table (it's Carter's own framework name). "Agent OS" is a lowercase descriptor only, never presented as the name.
— `01-overview/product-concept-overview-2026-07-08.md:163`, `:250`

---

## GAPS (things the exec-overview author needs that are missing or unresolved in the corpus)

1. **No precise ICP exists.** "C-levels first" is confirmed as a GTM motion, not a buyer definition. Counsel names this blind spot #1 (unit economics/pricing/ICP/buyer-ROI model) as still unfilled as of this extraction. If the exec overview needs a firmographic ICP line, it isn't in the corpus yet — flag it as "in progress" rather than inventing one.
2. **No data-governance/tenant-isolation one-pager exists yet** (blind spot #2). If the exec overview gestures at enterprise-readiness, do not imply this posture is written; it's roadmap (W9, month 1-2 per `07-roadmap/ROADMAP.md`).
3. **No founder operating-model/capacity-plan document exists yet** (blind spot #3) — relevant if the exec overview addresses "how does one operator do all this," which a sophisticated reader may ask given the Anchorage Sprint 1 (7/9-19) collision with this exact launch window.
4. **The 16x methodology memo (due 7/15) had not landed as of this extraction (7/9).** Whichever version of the exec overview ships before 7/15 must carry the output-parity fallback, not the raw multiplier.
5. **The exec-gui answer-relay spike (the one live, real front-door demo) does not exist yet.** Only the four published demo pages are currently real. Task #4 in the active task list ("W3 answer-relay spike + live front-door demo") is still pending — check before claiming a live front-door walkthrough is available for the room.
6. **No dedicated exec-overview-specific counsel pass exists beyond the two general per-deliverable briefs quoted in section 0.** Both the 2026-07-08 4-model panel verdicts and the 2026-07-09 deep-dives cover this deliverable only as one bullet among nine; there is no exec-overview-only critique file to cross-check a draft against once written.
7. **No confirmed visual/diagram exists in the corpus for either "the front door" or "the domino ladder."** The brief explicitly asks for "one strong visual" — this will need to be created by the exec-overview author or borrowed from a design pass; nothing in `06-deck-inputs/` was confirmed to contain a ready-made domino-ladder graphic (not fully verified this pass — worth a quick check of `06-deck-inputs/README.md` before assuming none exists).
8. **The exact BCG "40% RCT" and "13 rounds -> 1" figures' primary source was not independently re-verified this pass** — the overview cites them alongside the Anthropic Rakuten "24->5 days" stat as if from one lineage, but `03-execution/case-study-hardening.md` suggests the 24->5 days figure's real primary source is Anthropic's own 2026 report, not BCG. Reconcile which stat belongs to which source before the exec overview repeats them side-by-side (counsel item 12 already calls for sourcing named competitor/stat claims before deck use).
9. **"Two paying clients" tension (flagged at the top, repeating here as a formal gap):** the source overview names both clients (Anchorage and Upexi) in its own section 7/8, in direct tension with hard rule 3. No clean "safe to copy" sentence exists in the corpus that describes both clients without naming the second — the exec-overview author must write a new sentence (e.g., "two retained consulting clients, including Anchorage at $25k/mo") rather than lifting the source's phrasing.
