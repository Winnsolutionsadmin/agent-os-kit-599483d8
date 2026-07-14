# One-pager: extraction notes

**For:** the one-pager author/deliverable agent. **From:** research extractor sub-agent. **Date:** 2026-07-09.
**Corpus root:** `/Users/jarredwinn/Projects/agent-os-foundation` (all paths below relative to this root unless stated absolute).
**Time-box:** ~8 minutes target; actual run was longer because the exec-overview deliverable's own extract notes (already complete, independently verified) overlap heavily with one-pager needs and were worth mining in full rather than re-deriving from primary sources. Cross-citations to that file are marked `[via exec-overview notes]`.

Honest-math tags used below follow the task brief's own five-way schema: **MEASURED** (internal, verifiable), **SURVEY** (third-party polling), **VENDOR** (vendor-published, self-interested), **CORPUS** (internal estimate/count from this repo, not independently audited), **ASSUMPTION** (unverified, directional only). Where a source file uses `[unverified]` I map it to ASSUMPTION or CORPUS depending on whether it's a repo-internal count or a pure guess.

---

## 0. THE BINDING SPEC FOR THIS DELIVERABLE (read first, most authoritative last)

There are **two directives in the counsel corpus that conflict**, and the second/later one is explicitly marked BINDING. Both are quoted here so the author can decide; do not silently pick one.

**Earlier framing (raw panel distillation, gemini, `05-counsel/counsel-deepdive-2026-07-09.md:74` and again at `:108`):**
> "One-pager: teaser not architecture; frontier-lab brute force vs trusted companion matrix; next step explicit."
> "e) One-pager: ultimate elevator pitch; visual matrix of frontier-lab brute force vs trusted companion; clear next steps. Failure: explaining the whole architecture."

**Later framing (round-2 panel ADDENDUM 2, explicitly marked BINDING, `05-counsel/counsel-deepdive-2026-07-09.md:24`, under the header "DELIVERABLE SHARPENINGS (binding)"):**
> "One-pager: no 16x reference at all; three beats (what it is, why now, the ask) + link/QR to the reading room."

**My read, for the author to accept or override:** ADDENDUM 2 is same-day but later in the document and explicitly labeled binding, so it should govern the literal deliverable shape (three beats, no 16x, link/QR to reading room). The "frontier-lab brute force vs trusted companion" contrast is not necessarily dropped by ADDENDUM 2, it can live INSIDE the "why now" beat as a line or two of copy (see Section 3 below for ready-to-use phrasings) rather than as a rendered visual matrix, which would push toward "architecture" and risk violating the "teaser not architecture" spirit both directives agree on. If the author wants the literal matrix, the raw material to build one is in Section 3.

Task brief's own ask (verbatim, for cross-check): "the one-sentence definition, 3 proof points, the frontier-brute-force vs trusted-companion contrast, the pilot ask, contact line." This is consistent with both counsel framings blended: definition = "what it is" beat, proof points support "why now" or stand alongside it, contrast = the trusted-companion beat, pilot ask = "the ask" beat, contact line = closing.

---

## 1. The one-sentence definition ("what it is" beat)

Primary, full version, verbatim:
> "A gamified, AI-powered operating system for organizations: one calm conversational surface through which any employee, from CEO to line worker, directs and consumes agent work; org-level OKRs decomposed into weighted, agent-executed subtasks; adoption driven by game mechanics that reward people for using AI instead of threatening them with replacement; delivered as a consulting + software hybrid that takes cash + equity."
— `01-overview/product-concept-overview-2026-07-08.md:11` [via exec-overview notes, cross-verified against primary]

This is too long for a one-pager headline as-is; it is the "long form" to draw a one-liner from. Shorter category-line alternatives, all verbatim and pre-approved for external use, from `07-roadmap/W10-narrative-ledger/positioning-language-bank.md:13-19` section (a):
1. "We're the trusted companion that brings companies through the AI transition."
2. "Companies need a trusted companion to get through this transition. That's us."
3. "The labs build the capability. Someone still has to walk each company through the transition. We're that companion, and we hand them a head start."
4. "This isn't a tool you install. It's a companion that takes your company through the AI transition and leaves you ahead of it."
5. "What we sell is a head start: a trusted companion that carries a company through the AI transition faster than it could go alone."

Descriptor rule (same file, line 21): say "the system," "this platform," "what we're building," or "the companion." Never a name, never "the Agent OS" as if it were a brand — "agent OS" is a lowercase descriptor only per hard rule 1.

---

## 2. Proof-point candidates (more than 3 offered; pick sharpest 3 for space)

All MEASURED unless flagged. Source: `01-overview/product-concept-overview-2026-07-08.md` section 3 ("What has been built," lines ~43-51) as primary, cross-verified in `09-deliverables/exec-overview/_extract-notes.md` section 5.

- **Internal agent OS shipped org-wide, live since 2026-07-01.** [MEASURED]
- **claudecode-bar**, the internal fleet dashboard: 322 commits, 103-component UI, session-search recall improved from 8-10 seconds to 0.06 seconds. [MEASURED, CORPUS for the commit/component counts specifically]
- **the-sage**, the OKR scoring engine: 99.3% of 275/277 commits scored correctly on first run (self-scoring accuracy against ground truth). [MEASURED]
- **Achievement/gamification engine**: live since 2026-04-19, 5,027 points logged, 23-day streak never broken. [MEASURED]
- **Meeting-capture stack**: 343 processed meeting notes, ~47,000 embeddings generated. [MEASURED/CORPUS]
- **Skill registry**: 296 skills, 835 commits. [MEASURED/CORPUS]
- **Consultative delivery machine**: 6+ active consulting clients (67 archived over time). Anchorage named explicitly, $25k/mo signed. [MEASURED] **Only Anchorage may be named as a client. Do not name the second active client under any circumstance** — see Section 6 (naming trap) below.
- **Live demo pages** (treasury.html, fleet.html, triage.html, imessage.html) hosted at `winnsolutionsadmin.github.io/allan-ai-demos/`. [CORPUS — these exist and are viewable, but note per counsel ADDENDUM 2 overclaim-gate that demo data must be labeled honestly (built vs pilot-scope vs designed) if shown or linked]

Strongest-3 recommendation for a space-constrained teaser (my suggestion, not binding): (1) org-wide internal OS live since 7/1, (2) the-sage 99.3% scoring accuracy on first run, (3) Anchorage $25k/mo signed client. These three span "it's running," "it's accurate," and "someone already pays for it" — three different proof registers in minimal words.

---

## 3. The frontier-lab-brute-force vs trusted-companion contrast (raw material for either a matrix or prose)

Core premise framing, verbatim, from `positioning-language-bank.md` section (b) ("The frontier-lab premise, stated confidently," lines 25-34) — READ THE FULL RULE at line 34 first: **"never present lab capability as an existential risk to us... The organizing frame is always premise, not fear."**

1. "We know Anthropic and the other labs can do this. That's the premise of the market, not a threat to it."
2. "Yes, the labs can build this. That's exactly why every company now needs a companion through the transition. Capability arriving is what creates the demand."
3. Market-entry evidence, MEASURED: "The strongest evidence for this market is who just entered it. In May 2026 Anthropic launched a $1.5B enterprise AI services company with Blackstone, Hellman & Friedman, and Goldman Sachs, embedding Anthropic engineers inside portfolio companies. OpenAI followed a week later with a $4B deployment company." (MEASURED: Anthropic's own announcement plus CNBC, 2026-05-04; OpenAI's own announcement, 2026-05-11; full sources in `07-roadmap/W1-concept-doc-deck/competitor-sources.md`.)
4. "The labs entering the companion motion validates the category. What none of those ventures sells is our stack: scored objectives, consented mechanics, autonomy that's earned, not granted."
5. Skeptic-answer version: "They're already doing a version of it, at $1.5B, for Blackstone's portfolio. That's the market forming. The mid-market company that isn't a Goldman portfolio holding still needs a companion, and it needs one that starts from its own meetings, its own objectives, and its own people."

If the author wants a literal two-column matrix (per the earlier, non-binding gemini framing), the natural row set drawn from the above and from decision 0003 is:
| Frontier-lab brute force | Trusted companion (this) |
|---|---|
| Raw capability, general-purpose | Organizational psychology of adoption |
| Sold top-down as infrastructure | Earned bottom-up as trust, company by company |
| $1.5B-$4B services arms bolted onto the model | A companion that starts from a company's own meetings, objectives, and people |
| Capability without a relationship | A working reference estate (fleet-of-one) as proof, not just a pitch |

Strongest-conviction line to anchor either format, from a round-2 panelist (gemini), `05-counsel/counsel-deepdive-2026-07-09.md`: **"The moat is not the AI; it is the organizational psychology of adoption."** Also: kimi's "the only measure is one signed 90-day pilot"; glm's "the fleet-of-one IS the company"; grok's "radical honesty about capabilities is itself the moat."

Note on the disclosure/adoption-fear angle if "why now" needs sharpening beyond the lab-entry stat: the disclosure-penalty finding is strong but is about individual AI-use stigma, not company-level urgency, so it's a secondary option, not primary. [SURVEY/VENDOR] "94% of US knowledge workers report using AI at work, but in a controlled experiment, a peer who disclosed AI use was rated 10x lazier and was 24 percentage points less likely to be recommended for a high-visibility project, with identical output, versus a peer who did not disclose." (Atlassian research, 2026) — `03-execution/gamification-evidence.md:22` [via exec-overview notes].

---

## 4. The pilot ask (canonical, must appear verbatim if used at all)

**The one canonical ask sentence, binding across every artifact per the opus ADDENDUM (`05-counsel/counsel-deepdive-2026-07-09.md`):**
> "A scoped 90-day design-partner pilot plus a smaller strategic check. The larger raise comes at roughly month 6, triggered by demonstrated achievement."

Shorter derivatives, all pre-approved, from `positioning-language-bank.md` section (e) (lines 62-68):
1. "We're asking for a scoped 90-day design-partner pilot and a smaller strategic check. That's the whole ask."
2. "This isn't a raise. It's a pilot with named metrics, a written kill criterion, and a smaller check sized to the evidence."
3. "The pilot is the operator seat. The check is the owner seat. Two papers, never blended."

**Do NOT include on this deliverable:** any dollar figure for the pilot fee or retainer. A DRAFT-only pilot-fee working band exists ($45-60K for the 90 days; post-pilot retainer $20-30K/mo anchored on the Anchorage $25K/mo precedent) in `07-roadmap/W7-pilot-design/pilot-terms-skeleton-DRAFT.md`, but that document is explicitly disclaimed: "This document sends nowhere. Nothing in it is an offer, a price, a term sheet, or a solicitation of any kind." A teaser one-pager is very likely the wrong artifact for even a soft number; flagging as available raw material only, not a recommendation to use it.

**Do NOT include:** 16x, any multiplier, or any pricing/case-study number tied to the 16x claim. Per ADDENDUM 2, this deliverable specifically excludes 16x entirely (stronger than the general "16x needs lineage tag" rule that applies elsewhere in the kit).

---

## 5. Contact line

Only verified external-facing contact found in the corpus: **jarred@winn.solutions** (appears throughout the corpus as Jarred's working address; also used in the exec-overview deliverable). No phone number, LinkedIn URL, or company site was found anywhere in the corpus for this initiative (searched explicitly, no hits beyond email addresses). Suggested line: "Jarred Winn, founder — jarred@winn.solutions" per hard rule 5 (Jarred is THE founder, never "co-founder").

---

## 6. Naming / [NAME] motif and the client-naming trap

- **No naming candidates exist anywhere in the corpus.** Confirmed via the sibling `08-brand/_extract-notes.md` GAPS section: only illustrative archetype examples exist (structural/navigational e.g. Compass/Keel/Framework; ambient/calm e.g. Aura/Still/Clear; abstract/authoritative e.g. Vellum/Praxis), explicitly marked as "not a vetted shortlist." Ruled OUT explicitly: FleetView, TeamClaude GUI, gui-relay, mission control, Recurro, "Agent OS" (as a name).
- **No prior art exists for the "[NAME]" bracket-motif wordmark styling.** This is new to the task instructions, not sourced from the corpus. The author is originating this treatment fresh.
- **Client-naming trap (confirmed, high-risk copy-forward defect):** the primary source document (`01-overview/product-concept-overview-2026-07-08.md`, section 7/8) names Upexi inline as a second client, because it predates the correction that separated Upexi entirely from this initiative (hard rule 3). **Anchorage ($25k/mo, MEASURED) is the only client that may ever be named.** Any reference to a second client must stay generic ("a second retained consulting client") and never use the name Upexi, per exec-overview's own precedent-setting language and per hard rules 3 and 4 (Upexi and Mima both excluded entirely).

---

## 7. Style-compliance checklist (from the same corpus, apply to final copy)

From `positioning-language-bank.md` section (f), the anti-pattern table — the ones most relevant to a one-pager:
- No product name, including "Agent OS" as a brand → use "the system," "what we're building," "the companion."
- No fear-framed lab-capability line ("Anthropic could crush this") → use Section 3 premise-framing lines above.
- No "three founders," "co-founders," fixed splits → Jarred is THE founder; Nick and Carter are originating members earning equity through contribution.
- No "$10-50M raise" language.
- No "16x" — excluded entirely from this deliverable per ADDENDUM 2.
- No stat without a MEASURED/SURVEY/VENDOR/CORPUS/ASSUMPTION lineage tag available in source notes (tags don't need to render on the physical one-pager, but the author must be able to trace every number back to one).
- No readiness scores, internal bands, or rubric numbers.
- No "6-9 months of whitespace" or any month-count precision window.
- No em dashes, no double-hyphen ("--") punctuation anywhere (both are hard universal style laws).
- No cold-diligence psychology framing.
- Nothing premised on Upexi or Mima.

---

## GAPS (things the author needs that do not yet exist in the corpus)

1. **No "reading room" asset exists yet.** ADDENDUM 2 requires the one-pager to carry "a link/QR to the reading room," but the reading room itself is only specified as a future deliverable (tiered reading paths, built/designed legend, investor-vs-collaborator distinction, per `05-counsel/counsel-deepdive-2026-07-09.md:28`) — it has not been built. `06-deck-inputs/` and `08-partner-inputs/` each contain only a placeholder README. The closest existing stand-in is the live demo-page set at `winnsolutionsadmin.github.io/allan-ai-demos/`, but that is a demo, not a reading room, and using it as the QR target would need the honest-math/demo-labeling overclaim gate applied first.
2. **No vetted naming candidates exist**, only illustrative unvetted archetype examples (see Section 6). The founder has not named the product, so the one-pager's "[NAME]" bracket motif is inherently a placeholder with nothing to fill it once named.
3. **No prior art for the bracket-motif wordmark treatment itself** — this is a new design convention being introduced by the task, not something the corpus has already solved.
4. **Directive tension not resolved** (see Section 0): "no 16x, three beats" (binding, later) vs "frontier-lab brute force vs trusted companion matrix" (earlier, non-binding but directly responsive to what the task brief asked me to extract). The author/founder should explicitly decide whether the contrast renders as a visual matrix, a prose beat, or is dropped, rather than the extractor or a downstream agent silently picking.
5. **Pilot pricing is DRAFT-only and explicitly disclaimed** ("sends nowhere... not an offer"). If any soft price signal is wanted on the one-pager, it does not yet have an approved, undisclaimed source number.
6. **No confirmed contact channel beyond email** — no phone, no LinkedIn, no company/site URL found anywhere in the corpus for this initiative specifically.
7. **The "two clients" framing is a live naming trap** carried in the primary source document itself (predates the Upexi correction) — flagged in Section 6, but worth restating here as a GAP in the sense that the primary source cannot be safely copy-pasted from without this edit applied by hand every time.
8. **No one-pager visual/layout template exists** — this is a from-scratch design task; no draft, wireframe, or precedent for one-pager layout was found in the corpus (unlike the 16-slide deck skeleton, which exists at `07-roadmap/W1-concept-doc-deck/deck-skeleton.md`).
