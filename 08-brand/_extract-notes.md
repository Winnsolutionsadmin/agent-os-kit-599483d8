extraction pass, brand-package deliverable

Compiled 2026-07-09 for the business-launch kit's brand-package author. Method: full read of `CLAUDE.md` (8 authoritative corrections) and `05-counsel/counsel-deepdive-2026-07-09.md`, plus targeted rg across the corpus for positioning language, founder voice, category naming, and the counsel naming process. Time-boxed to roughly 8 minutes; see GAPS at bottom for what a full pass would still need to cover.

**Update pass (same day, second extractor):** `05-counsel/counsel-deepdive-opus-2026-07-09.md` has since landed on disk (it did not exist at the time of the first pass; see the now-corrected note in GAPS #4 below). It is the second, independent panelist voice and materially deepens the naming-process material and the brand-package deliverable spec specifically. Section 4a and the 5b gate list below fold in its deltas. Also spot-checked the three 04-competitive landscape dossiers not cited in the first pass (`landscape-consulting-hybrids.md`, `landscape-gamification-vendors.md`, `landscape-marketplace-attribution.md`) for naming-convention material; one useful addition folded into section 3. Confirmed via `find 09-deliverables -type f` that no brand-package deliverable draft exists yet elsewhere in the repo (only `founder-memo/_extract-notes.md` exists as a sibling raw-material file; exec-overview, pitch-deck, whitepaper folders are empty) and via `rg -i mima` awareness that two corpus files (`02-sweep/swarm-mima.md`, `02-sweep/mima-mini-corpus.md`) exist but are correctly excluded from this extraction per hard rule #4 (Mima excluded entirely).

All quotes below are verbatim from the cited file. Do not paraphrase them back into deck copy without the citation.

---

## 0. Hard constraints this deliverable must honor (recap, not exhaustive; CLAUDE.md is authoritative)

- Product and company are UNNAMED. "agent OS" is a lowercase descriptor only, never presented as a decided name. Brand-package output presents naming CANDIDATES; founder decides.
- Recurro = Carter Razink's own agentic-engineering framework. Never the product/company name.
- Completely separate from Upexi; never mention it. Mima excluded entirely; never mention it.
- Jarred Winn is THE founder. Nick Metzler and Carter Razink are originating members earning equity through contribution. Never "co-founders" / "three founders" / fixed splits.
- No em dashes, ever. No double-hyphen punctuation.
- Every stat needs a tag lineage (MEASURED / SURVEY / VENDOR / CORPUS / ASSUMPTION per this task's schema; corpus itself uses MEASURED/SURVEY/VENDOR/[unverified]).

---

## 1. Positioning language (verbatim, for brand voice/copy mining)

### Trusted companion + head start (the core positioning)

Source statement, Jarred verbatim (`05-counsel/grasp-verification-2026-07-08.md:3`, also `memory-bank/decisions/0003-founder-structure-funding-positioning.md:6`):
> "we would raise funding based on achievement and faith from investors we know already. we know that anthropic etc. can do this, but companies need trusted companions to bring them through this and help them get a headstart. Dominos fall as: C-levels first, chief of staff/organizer. Engineers next, revamp/overhaul. All else follows based on demand. I am the founder of this. We want to develop this in a manner in which contribution can earn equity for originating members (being them) but the vision is mine."

Binding interpretation (`memory-bank/decisions/0003-founder-structure-funding-positioning.md:16`):
> "their capability is ACKNOWLEDGED AND ASSUMED ('we know Anthropic etc. can do this'). The category we occupy: the TRUSTED COMPANION that brings companies through the transition and gives them a head start. Platform capability is the premise of the market, not primarily a threat to us; fear-framed platform-capture analysis is repositioned accordingly (hedges remain engineering hygiene, not existential posture)."

CLAUDE.md house version (`CLAUDE.md:13`):
> "Trusted-companion positioning. Anthropic and peers CAN build this; that capability is the market premise, not our existential fear. The category we occupy: the trusted companion that brings companies through the AI transition and gives them a head start. Platform hedges remain engineering hygiene."

ROADMAP one-line positioning statement (`07-roadmap/ROADMAP.md:3`):
> "Positioning: the trusted companion that brings companies through the AI transition and gives them the head start."

Strongest conviction, counsel deep-dive (`05-counsel/counsel-deepdive-2026-07-09.md:39` and `:90`):
> "the moat is not the AI; it is the organizational psychology of adoption. The kit succeeds if it makes a known investor feel this is the team they would trust to guide their own companies through the transition." / "Pair elite technical leverage (Recurro) with deep human empathy (gamified anti-abuse, calm UI, consultative delivery): you are selling the safest bridge across the AI transition."

Frontier-lab concession framing, distilled directive (`05-counsel/counsel-deepdive-2026-07-09.md:13`):
> "Frontier-lab narrative: concede capability, pivot hard to capabilities-do-not-equal-adoption; moat = organizational psychology + gamification + trusted-companion delivery."

QA gate on this exact point (`05-counsel/counsel-deepdive-2026-07-09.md:24`):
> "Frontier-lab immunity is never claimed: concede the tech baseline; the moat is adoption psychology and trust."

### Calm (product feel, brand tone)

Product one-liner (`01-overview/product-concept-overview-2026-07-08.md:11`):
> "A gamified, AI-powered operating system for organizations: one calm conversational surface through which any employee, from CEO to line worker, directs and consumes agent work..."

Must-have law #8 (`01-overview/product-concept-overview-2026-07-08.md:138`):
> "Calm by default: only the one thing that needs the human pulses; false positives are product failures."

GUI dossier, "calm by default" as an actively enforced anti-pattern (`02-sweep/swarm-gui.md:53`):
> "Calm by default: only the one tile or signal that truly needs the human pulses; false positives ('crying wolf') are treated as product failures to be actively fought, not tolerated (claudecode-bar)."

"One window of consequence" framing (`02-sweep/swarm-gui.md:95`):
> "a single calm, conversational surface through which a decision-maker... directs and consumes agent work with no code or tool-call noise, with the triage layer eventually absorbing most routine choices so only high-leverage decisions ever reach a human."

Counsel brand brief ties calm directly to trust and to the naming problem (`05-counsel/counsel-deepdive-2026-07-09.md:28`, `:62`):
> "Brand: calm, structural integrity, trust; 3 archetype directions... Failure: trendy consumer-app naming or tech-bro aggression undermining the calm trusted-companion premise."

Note on register consistency: `05-counsel/grasp-verification-2026-07-08.md:48` and `:68` flag that the corpus itself sometimes lapses into "existential" framing (fear of Anthropic/platform capture) alongside the calm/engineering-hygiene register, and that the calm register is the one decision 0003 requires. Useful caution for brand voice: existential-threat language about frontier labs must not leak into brand copy; concede-and-pivot only.

### Human gates / graduated autonomy (product-law language, useful for "trust" proof points)

`CLAUDE.md:29`:
> "Product law (counsel: 'don't touch it'): never auto-act on money, irreversible, or external actions without a human gate; autonomy is earned via graduation (90% agreement over 20+ reps per decision class)."

Counsel deep-dive QA gate phrasing (`05-counsel/counsel-deepdive-2026-07-09.md:21`):
> "Autonomy = the system orchestrates; humans execute the final gate (Approve/Edit/Skip; graduated autonomy 90%/20-reps). Never 'runs your company.'"

Counsel verdict on this law (`05-counsel/counsel-verdicts-2026-07-08.md:25`, claude panelist):
> "best-specified, most falsifiable governance item; don't touch it."

The literal UI verb set for the human-gate interaction, used everywhere in the corpus: **Approve / Edit / Skip** (e.g. `01-overview/product-concept-overview-2026-07-08.md:27`, `04-competitive/landscape-agent-startups.md:11`). This is the recurring named mechanic; brand/visual language should treat it as a fixed term of art, not a paraphrase target.

### Reward-not-replace (adoption thesis, differentiator vs. every competitor found)

Core adoption thesis, verbatim from the founding call (`01-overview/product-concept-overview-2026-07-08.md:15`):
> "We're not doing this so you can replace your employees, we're doing this so you can reward your employees and retain them based on the fact that they are then going to be adopting AI."

Scorecard law #18 (`01-overview/product-concept-overview-2026-07-08.md:150`):
> "Reward-not-replace framing is the adoption contract (opt-in bonus pools, e.g. the $250k-pool example)."

Competitive-landscape confirmation that this is genuinely differentiated language, not table stakes (`04-competitive/landscape-meeting-workgraph.md:101`):
> "'Reward, not replace' framing is absent. All twelve players frame agents as doing work a human used to do... efficiency/replacement logic. None frame agent output as something that earns the employee comp, time-back, or recognition. This is a messaging and mechanic gap our pillar 3 fills directly."

Same point, incumbents dossier (`04-competitive/landscape-incumbents.md:84`):
> "'Reward, not replace' as explicit branded philosophy. Every vendor here frames agents as headcount-saving 'digital labor' (Salesforce's own word) or ticket-deflection (ServiceNow's 90% auto-resolution claim). Nobody is messaging gamified adoption as an explicit anti-fear, retention-linked employee pact the way our concept states it ('reward employees... versus people being worried about losing their job')."

Real-world existence proof this contract is payable, not just a pitch line (`03-execution/gamification-evidence.md:18`):
> "1Mind (CEO Amanda Kahlow): spot bonuses for employees who identify automation opportunities, with forward-vesting equity under consideration for anyone who 'automates themselves out of a role.'"

Contrast set (what NOT to sound like, `03-execution/gamification-evidence.md:19`):
> "Accenture and Coinbase, by contrast, reportedly used threat framing ('adopt AI or risk your career') rather than reward framing. Starbucks pegged roughly a quarter of tech-team bonuses to AI adoption." (CORPUS/VENDOR, sourced to Reejig/Bloomberg in that file)

Cautionary tale worth carrying into brand tone-of-voice guidance (backlash precedent if reward mechanics are ever mishandled, `04-competitive/risk-gamification-backlash.md:11`): Meta's "Claudeonomics" leaderboard (abolished one day after press exposure, 60.2 trillion tokens burned in 30 days at roughly $900M list price) and Amazon's "KiroRank" (deprecated after workers gamed it) are named precedents for why anti-abuse and reward-not-replace framing has to ship day one, not as an afterthought. Useful for a founder-memo "what we refuse to become" beat, not brand-name material.

---

## 2. Founder voice traits (honest math, zero overclaim, operator directness)

### Honest math (mechanical rule, applies to every artifact)

`CLAUDE.md:28`:
> "Honest math: every stat carries a MEASURED / SURVEY / VENDOR / [unverified] tag lineage; loop-deletion framing over raw multipliers; no overclaim. The 16x case study is NOT deck-usable until Carter's methodology memo lands (due 7/15); fallback framing is output-parity ('4 matched the output of 18')."

Overview law #20 (`01-overview/product-concept-overview-2026-07-08.md:154`):
> "Honest math in all external material: sourced stats, loop-deletion framing instead of raw multipliers, no overclaim (the 88%-to-1% walkback discipline)."

The "88% to 1%" walkback is the concrete proof-of-discipline example: an initial 88 percent adoption headline was deliberately killed as overstated for the real subject matter (`02-sweep/swarm-allan-marshall.md:49`):
> "An explicit 'honest math' discipline running through the whole deck: no claimed stat is allowed past a MEASURED/SURVEY/VENDOR/[unverified] source tag; the headline 10x claim is reframed as loop deletion (e.g., '13 rounds to 1' or '24 days to 5'), not raw task-time compression, and an initial 88 percent adoption headline was deliberately killed as overstretched for Allan's real subject matter."

### Zero overclaim (named discipline, cited as a KPI in its own right)

`02-sweep/swarm-anchorage.md:43`:
> "Zero overclaim. The deck's own stated rule: every loud moment must be backed by a real thing. Sprints 2-4 are explicitly principle-grade placeholders, never presented as commitments. 'Zero overclaim leaks' is the stated honesty KPI."

Same discipline applied to the 16x number specifically, with the exact fallback language to reuse (`03-execution/case-study-hardening.md:99`):
> "if Carter cannot produce a defensible package by 7/15, demote the number out of the pitch's lead slide and carry it only as a footnoted internal data point pending a rigor pass... consistent with the estate's own stated law that external material must use honest math and never overclaim."

### Operator directness / no hype (founder voice red lines, from the closest analog to a "how Jarred sounds" spec on file)

These are drawn from `02-sweep/swarm-allan-marshall.md` (the most detailed on-file voice/style discipline for a named-recipient deliverable; belief-indexed to Allan specifically, but the mechanical rules generalize and match the founder's own stated instincts elsewhere in the corpus):
> "No hype, no forward-looking promises, no crypto slang, no 'I built' framing, never position [recipient] as an 'AI personality.' These are explicit, written red lines in `talk-track.md`..." (`:49`)
> "Chart-plus-minimal-narrative, no em dashes, infographic-dense (never plain stat tiles)." (`:50`)
> "Numbers must be sourced and honest, even if that means a smaller number." (`:51`)

Counsel's founder-memo brief names the exact voice target directly (`05-counsel/counsel-deepdive-2026-07-09.md:32`, `:66`):
> "Founder memo: Jarred's idiosyncratic voice, zero overclaim, fleet-of-one origin story, philosophical enemy = chaotic AI adoption." / "authentic zero-overclaim voice; 10-year horizon grounded in the fleet-of-one origin; define the philosophical enemy (chaotic AI adoption). Failure: sanitized AI-sounding corporate jargon."

Pitch-deck brief, same register (`05-counsel/counsel-deepdive-2026-07-09.md:27`, `:61`):
> "lead with founder insight + fleet-of-one proof; adoption psychology over architecture... Failure mode: selling the tech instead of the adoption psychology." / "emphasize why-us (organizational psychology and gamification) over what (the AI)."

"The fleet-of-one estate IS the demonstration" (recurring founder-voice anchor line, `01-overview/product-concept-overview-2026-07-08.md:19`):
> "Jarred already runs the reference implementation. His own estate IS the product at fleet-of-one scale... 'This deck is the demonstration' generalizes to: this operation is the demonstration."

Operator/directness tone example from the raw call transcript itself, useful as a founder-voice register sample (`00-call-notes/raw/2026-07-08-fieldy-raw.jsonl:118`, transcript, informal register, cite as raw source only, not for direct quotation in polished materials):
> "right now we're in between the window where we can give this head start to all these businesses that want to start it now and get that benefit but they still need our minds in order to get there... I would look at money as a reflection of the speed that we'd want this to get out at."

---

## 3. Category landscape naming conventions (from 04-competitive dossiers)

Naming patterns actually in market right now, useful as a reference set for what reads credible vs. generic in this category:

- **Short abstract/proper nouns:** Sierra, Dust, Glean, Bond, Cognition, Factory.
- **Descriptive compounds:** WorkBoard, LangChain.
- **Literal function-as-name (the pattern to avoid):** Sierra's own product is branded, verbatim, **"Agent OS"** (`04-competitive/landscape-agent-startups.md:11`, `:40`, `:90`):
  > "Sierra's own product is literally named 'Agent OS,' which is a direct branding collision worth knowing about even though its scope (external customer-service agents) is different from ours (internal, whole-org)." Sierra: $950M raised at $15.8B valuation (2026-05-04), ~$200M ARR, >40% of Fortune 50 as customers (~700 employees), per TechCrunch/CNBC/Latka citations in that file. TAG: CORPUS (secondary reporting, not independently re-verified by this extractor).
  - Competitive scorecard: "Owns the literal phrase 'Agent OS' and has $1B+ in fresh capital to expand scope, but is architecturally external/customer-facing and priced per resolution." (`:90`)
- ServiceNow's product is literally named **"AI Agent Orchestrator"** (`04-competitive/landscape-incumbents.md:52`), ranked #1 by Gartner's 2025 Critical Capabilities report.
- Dust brands itself the **"multiplayer" operating system for enterprise AI** (`04-competitive/landscape-agent-startups.md:42`), the closest positioning collision to the calm-front-door pillar.
- Meta's internal gamified AI-adoption program is named **"Level Up"**; its abandoned leaderboard was informally called **"Claudeonomics"** (`04-competitive/landscape-agent-startups.md:11`; `04-competitive/risk-gamification-backlash.md:11`). Amazon's was **"KiroRank."** These read as case studies/cautionary precedent, not naming inspiration.
- Direct implication for the brand deliverable: **"Agent OS" and close variants ("AI Agent Orchestrator," "[X] OS" as a literal product name) are already occupied/collided in this exact category.** This corroborates hard rule #1 (agent OS stays a lowercase descriptor, never the name) with a live competitive citation, and is a strong argument to keep well clear of "OS," "orchestrator," "agent," and "-AI" as load-bearing words in any actual candidate name.
- Category-wide naming climate: as of mid-2026, Microsoft, Google, ServiceNow, Salesforce, and EY have all shipped or GA'd an "agent OS" or functionally equivalent bundled orchestration layer (`04-competitive/risk-timing-commoditization.md:11`), meaning the generic descriptor is now market-saturated language, reinforcing the need for a genuinely distinct name rather than a descriptive one.
- Live "-AI suffix" example in the wild, reinforcing the avoid-list below with a real precedent rather than a hypothetical: Spinify markets itself with "Direct — 'AI Coaching Agent,' 'AI Gamification' branding" (`04-competitive/landscape-gamification-vendors.md:20`), and is separately described as "the closest existing brand-level claim to 'AI gamification'" while being "[t]oo small/niche to threaten an enterprise OS play directly" (`04-competitive/landscape-gamification-vendors.md:43`, `:97`). Useful as a concrete "this is what the ages-poorly/commoditized register already looks like in our own category" example.

---

## 4. Counsel naming process (the actual brief for this deliverable)

This is the most direct, on-point material in the corpus for the brand-package author; it comes straight from `05-counsel/counsel-deepdive-2026-07-09.md` (gemini panelist, section 4 and section 2b), reconciled with the CLAUDE.md placeholder-wordmark ruling.

**Three archetype directions** (verbatim naming examples are the panel's own illustrative candidates, not vetted/cleared; treat as archetype demonstrations only, not shortlist-ready):
1. **Structural/navigational** — e.g. Compass, Keel, Framework.
2. **Ambient/calm** — e.g. Aura, Still, Clear.
3. **Abstract/authoritative** — e.g. Vellum, Praxis.

(`:80`): "Archetype generation across structural/navigational (Compass, Keel, Framework), ambient/calm (Aura, Still, Clear), abstract/authoritative (Vellum, Praxis)."

**Clearance checklist per candidate:**
> "USPTO TESS collision checks (classes 9 and 42). Domain sanity: premium modifiers or tier-1 alternates (.co/.io/.ai), no hyphens; GitHub and app-store overlap checks." (`:80`)

**Explicit avoid-list:**
> "Avoid: the 'AI' suffix (ages poorly, commoditizes), aggressive automation terms (Blitz, Auto, Sync, Force), whimsical names that cannot command boardroom respect." (`:80`)

**Brand brief musts/failure mode** (`:28`, `:62`):
> "Brand: calm, structural integrity, trust; 3 archetype directions (structural/navigational, ambient/calm, abstract/authoritative); domain and USPTO class 9/42 sanity per candidate; avoid the -AI suffix, aggressive automation words, whimsy." / "evoke calm, structural integrity, trust; 3 naming directions (authoritative, navigational, foundational); enterprise-grade domain clarity. Failure: trendy consumer-app naming or tech-bro aggression undermining the calm trusted-companion premise."

**Placeholder-wordmark ruling, reconciled** (item 10 in the top-10 list, `:17`, `:58`):
> "Cohesive placeholder treatment in all materials: the product is UNNAMED by founder ruling; the kit uses a clean placeholder wordmark and presents naming CANDIDATES only." / "Establish a Working Codename: cohesive presentation projects competence. [Reconciled with decision 0003: the kit uses a placeholder wordmark and candidates; the founder names the company.]"

Note: nothing in the corpus specifies the exact "[NAME]" bracket-motif styling described in this task's hard rules; that visual/typographic treatment is new to this deliverable, not sourced from the corpus. It does not contradict anything on file, it simply has no prior art here (see GAPS).

---

## 4a. Opus panelist addendum — deepened naming process + brand-package deliverable spec (`05-counsel/counsel-deepdive-opus-2026-07-09.md`)

This is a second, independent panelist voice (seated after grok/codex/claude-mini failed; did not read the gemini file first) and is considerably more operational than section 4 above. Treat the two as convergent, not conflicting: both prescribe 3+ archetype/territory directions, a same-day USPTO class 9/42 + domain knockout screen, and an avoid-the-"-AI"/avoid-aggressive-automation-words list; opus adds a concrete 8-step sequence, explicit anti-pattern example names, and a specific brand-package deliverable spec.

**Brand-package deliverable musts, verbatim** (`:47-51`, section "(b) Brand package, naming CANDIDATES only"):
> "Present 3 to 5 named territories (for example: calm-companion, operating-surface, trust-and-attestation, orchestration/cartography), each with 2 to 3 candidates, a rationale, and the feeling it evokes; never rank one as the pick."
> "Run a same-day knockout screen on every survivor: trademark exact and phonetic in classes 9 and 42, live .com and .ai domains, GitHub/npm/PyPI org, social handles, existing-AI-company collision. Present the screen results with the names."
> "Explicitly retire the ruled-out names in the doc (FleetView, TeamClaude GUI, gui-relay, mission control) and restate that Recurro is Carter's own framework, off the table; and that 'Agent OS' is a descriptor, not a candidate."
> "Apply trust-positioning constraints: avoid names that overclaim autonomy or omniscience, avoid surveillance registers, favor calm/partnership/human-agency, 2 to 3 syllables, spellable on first hearing."

**Named failure mode** (`:51`):
> "presenting a single favorite dressed up as 'options,' which usurps the founder's explicit decision right, and burning the screen on names that turn out legally dead."

**Names to explicitly retire in the brand doc** (actionable, not a gap): FleetView, TeamClaude GUI, gui-relay, mission control — these are prior working-title/internal-tool names surfaced elsewhere in the estate that opus flags by name as ruled-out candidates the brand doc should explicitly close off, alongside restating that Recurro (Carter's framework) and "Agent OS" (a descriptor) are off the table as product/company names. This directly operationalizes hard rules #1 and #2.

**The 8-step naming sequence, verbatim** (`:133-147`):
1. "Territory before name. Define 3 to 5 naming territories tied to the positioning (trusted companion, calm operating surface, attestation and origin, orchestration or cartography) and name the feeling each evokes. The founder should pick a direction before a word." (`:133`)
2. "Set 2026 trust-brand constraints up front. Avoid names that overclaim autonomy or omniscience (registers like Omni, God-mode, Overlord, Autopilot spook enterprise buyers whose whole concern is control). Avoid 'Agent' as the literal brand (category-generic, and a descriptor here). Avoid surveillance connotations. Favor calm, partnership, guidance, and human agency. Aim for 2 to 3 syllables, spellable and pronounceable on first hearing." (`:135`)
3. "Generate broad, then cut hard. Produce 20 to 40 candidates across the territories using human plus model generation, then cut by the feeling and by the enterprise-buyer register, not by cleverness." (`:137`)
4. "Run a same-day knockout screen on the survivors (this is where most names die). Trademark exact and phonetic search in classes 9 (software) and 42 (SaaS); live .com and .ai availability (a trust brand needs a real domain, not a workaround); GitHub, npm, and PyPI org names; social handles; a collision check against existing AI companies; and a 'say it on a phone' test." (`:139`)
5. "Clear legally at trust-brand depth. A knockout search now, a full attorney trademark-availability search before any spend, and an intent-to-use filing on the top one or two candidates before public launch. A trust-positioned company cannot afford to rename after launch." (`:141`)
6. "Run a linguistic and cultural check. No unfortunate meanings in major languages, no negative connotations, and ideally it works as a verb." (`:143`)
7. "Present candidates with rationale and screen results to the founder, never a single ranked pick. The founder decides. The moment he decides, lock the domain, handles, and trademark filing that same week." (`:145`)
8. "Reserve a descriptor line so the name need not explain itself (for example '[Name], the trusted companion for the AI transition'). This frees the name to be evocative rather than literal, which is what a durable enterprise brand needs." (`:147`)

Note on step 8: this is the closest thing on file to a tagline/descriptor-line pattern (see GAPS #7) and pairs directly with the "trusted companion... head start" positioning language in section 1 above; e.g. "[Name], the trusted companion for the AI transition" is opus's own illustrative example, not a cleared candidate.

Note on step 2's anti-pattern list (Omni, God-mode, Overlord, Autopilot): these read as a useful negative-example set specifically for the "aggressive automation" and "overclaims autonomy" avoid-categories in section 4 above, sharper than gemini's Blitz/Auto/Sync/Force list because they're framed around the trust/control anxiety of an enterprise buyer rather than generic tone.

---

## 5. Overclaim gates as brand copy guardrails (mechanical, quote for the style guide section of the brand doc)

Full gate list, verbatim (`05-counsel/counsel-deepdive-2026-07-09.md:19-24`):
> "16x = internal benchmark achieved with Carter Razink's Recurro framework, methodology memo pending; never generalized to customer outcomes."
> "Autonomy = the system orchestrates; humans execute the final gate (Approve/Edit/Skip; graduated autonomy 90%/20-reps). Never 'runs your company.'"
> "Traceability over perfection: never zero-hallucination or perfect-accuracy claims; promise provenance and auditability."
> "Integration honesty: legacy integration is real friction; the consultative companion is the bridge, not magic."
> "Frontier-lab immunity is never claimed: concede the tech baseline; the moat is adoption psychology and trust."

These read directly as the "voice and claims" section of a brand guide, i.e. the things a tagline or brand one-liner must never imply.

### 5b. Second independent convergence (opus panelist, `05-counsel/counsel-deepdive-opus-2026-07-09.md:151-161`)

Opus derived its own 5-gate list independently (did not read the gemini file first) under the header "The 5 places polish tips into overclaim for AI startups, and the QA gate for each." Two are new framings not explicit in section 5 above and worth carrying into brand-doc style guidance directly:
> "Roadmap rendered in the present tense. Polish turns 'will have multi-tenancy' into 'has.' Gate: a built-versus-designed tag on every capability claim... Externally, only Tier A and B capabilities speak in the present tense." (`:153`)
> "Demos implying a scale that does not exist. Polish presents a fleet-of-one reference implementation as a multi-tenant product live at paying customers. Gate: every demo and proof is labeled reference implementation / fleet-of-one... Never imply live multi-tenant paying usage that is not there." (`:159`)

The other three (multipliers-as-headlines/16x, survey-stats-laundered-into-fact, the-ask-inflating-past-evidence) are the same substance as section 5's gates, independently re-derived, which is itself useful signal for the brand doc: two independent panelists converged on the same guardrails without cross-reading each other.

---

## 6. Fleet-of-one proof numbers (brand credibility material; tag classification is this extractor's addition per the task's MEASURED/SURVEY/VENDOR/CORPUS/ASSUMPTION schema, not the corpus's own tagging, since the source files state these as flat facts without a tag)

- 23-day unbroken gamification streak (CORPUS; `04-competitive/competitive-risk-2026-07-08.md:130`, `04-competitive/redteam-moat.md:101`)
- 99.3 percent first-run OKR-alignment accuracy across 277 real commits (CORPUS; same two files)
- 296-skill registry, 835 commits (CORPUS; same two files)
- 322 commits on claudecode-bar, the fleet HUD (CORPUS; `01-overview/product-concept-overview-2026-07-08.md:45`)
- 343 processed meeting notes and 47k embeddings (CORPUS; `04-competitive/redteam-moat.md:101`)
- 16x engineering claim: explicitly NOT deck-usable / NOT brand-copy-usable until Carter's 7/15 methodology memo; fallback is output-parity framing "4 matched the output of 18" (ASSUMPTION pending methodology; `CLAUDE.md:28`, `05-counsel/counsel-deepdive-2026-07-09.md:20`)

These are strong "operator directness" proof points for founder-memo/pitch-deck voice, but every one is internal/self-reported (CORPUS tag), not independently audited. Flag this plainly if used in brand copy claiming credibility ("measured internally," not "measured").

---

## GAPS (things the brand-package author will not find in this corpus and should ask for or generate fresh)

1. **No actual naming candidates exist yet.** The archetype/territory examples across both panelists (section 4: Compass/Keel/Framework, Aura/Still/Clear, Vellum/Praxis; section 4a: calm-companion, operating-surface, trust-and-attestation, orchestration/cartography) are illustrative examples from the counsel process, not a vetted shortlist, and not run through the USPTO/domain knockout screen both panelists prescribe. The brand-package author needs to generate and clear real candidates from scratch using the section 4a 8-step process; nothing in the corpus does this work already.
2. **No prior art for the "[NAME]" bracket-motif wordmark styling.** The corpus establishes the placeholder-wordmark *principle* (clean placeholder, candidates only, founder decides) but not this specific bracket typographic treatment. This is new to the task instructions, not sourced from the corpus; treat it as this deliverable's own design decision, not something to hunt for further.
3. **No visual/color/typography direction on file anywhere in this corpus.** All "calm, structural integrity, trust" language is verbal/positioning, not a palette, type system, or logo direction. `06-deck-inputs/README.md` points to `/stylize` and "house-style HTML for anything client-facing" as the only concrete style mechanism referenced, but no brand-specific visual system exists yet.
4. **RESOLVED as of this update pass:** `counsel-deepdive-opus-2026-07-09.md` was not on disk during the first extraction pass earlier today; it has since landed and section 4a / 5b above fold in its brand-relevant deltas (the 8-step naming sequence, the brand-package deliverable spec with named territories/knockout-screen/never-rank-one-favorite, the explicit names-to-retire list, and its independently-derived overclaim gates). Still true: only 1 of 4 *external* panelists (gemini) answered the original deep-dive; grok/codex/claude-mini failed; opus is a local second seat, not one of the original four. No third or fourth external voice on naming exists.
5. **No trademark/USPTO search has actually been run.** The checklist (class 9/42, TESS collision, domain/GitHub/app-store overlap) is prescribed in detail by both panelists but not executed anywhere in the corpus for any real candidate.
6. **Company/entity name and product name relationship is unaddressed.** Nothing in the corpus says whether the company name and product name are meant to be the same word or different (common in this category, e.g. Sierra the company vs. Agent OS the product line). Worth a founder decision point, not something to assume.
7. **No tagline or one-line brand promise exists yet**, only positioning paragraphs. The "trusted companion" / "head start" language is the strongest raw material for one but has not been distilled into a candidate tagline anywhere on file.
8. **Voice-guide material is Allan-specific, not house-general.** The clearest on-file "how Jarred sounds" spec (`02-sweep/swarm-allan-marshall.md`) is explicitly belief-indexed to one recipient (Allan Marshall) for a teaching deck, not a general house style guide. A general founder-voice style guide for this venture (as opposed to per-recipient belief-indexing) does not exist yet in this corpus; section 2 above generalizes cautiously from it plus the CLAUDE.md/counsel-deepdive rules, but a dedicated pass may be warranted if the founder wants a formal voice doc.
