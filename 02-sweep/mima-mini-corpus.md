---
title: Mima corpus sweep (mini workspace)
scope: read-only investigation of ~/.openclaw/workspace on mini (user clawd)
date_compiled: 2026-07-08
method: grep -i -C 6 on large files, full reads on key meetings, one recursive sweep for aliases
---

# Mima: definition, evolution, and relationship to the Agent OS concept

This dossier answers three questions from a read-only sweep of Jarred Winn's CRM/memory
workspace on the mini (`~/.openclaw/workspace`, ssh mini, user clawd): what Mima is, how it has
evolved from March through July 2026, and whether it connects to the newer "Agent OS" / "RSI for
orgs" concept being built with Nick Metzler and Carter Razink (working name candidate
"Recurro"). Nothing on the mini was modified during this investigation.

## What Mima is (definition)

Mima is Jarred Winn's own personal, consumer-facing product concept: an agentic personal AI that
triages a person's life (priorities, communications, opportunities) while verifying that actions
and identity are human-authorized through a zero-knowledge proof layer called Trust Origin, with
a stated long-term path to becoming a blockchain layer-1 (L1) identity and agent protocol. The
earliest investor-facing codename for the same concept is "Project X." Tagline recorded in
`working-with-jarred.md`: "your AI. your identity. your data." The roadmap is explicitly
three-phase: product ($49/mo) then platform (a relationship knowledge graph) then protocol
(on-chain identity, an agent marketplace, ZK proof-of-human).

`priority-stack.md` (created 2026-03-17, status active) ranks it directly under Winn.ventures in
Jarred's business priority list: "Project X / Mima (Mima) - consumer Personal AI, agentic
triaging, ZK-proof human verification ('Trust Origin'), path to L1. Prototype exists. Ethereum
Foundation (Tomas) interested. The big bet."

Mima is explicitly distinct from two adjacent things Jarred also builds: OpenClaw (his internal
multi-agent operating system, used to run his own life and business) and Winn.solutions (his
public consulting brand). `working-with-jarred.md` states a HARD RULE that Winn.solutions must
never reference OpenClaw or Mima publicly; both are internal-only tooling and personal bets.

## Feature set and concepts attached to Mima

- Agentic triaging of a person's priorities, communications, and opportunities. Jarred's own
  framing, from the 2026-06-11 meeting: "My dream when I was first starting a business was I was
  like to have an executive assistant that was as plugged into my priorities as I was."
- Trust Origin: a zero-knowledge proof-of-human-authorization layer. Framed explicitly as not
  constraining or "shackling" AI, but verifying that a human authorized an action.
- On-device and open-source requirements, validated in conversation by Chappie (see below):
  "This has to be fully on device. This has to be, I think, fully open source because this is
  touching like all of your most private sensitive things."
- A relationship knowledge graph and belief-index system, shared by Jarred as an integration
  reference for a peer's relationship-intelligence platform.
- Path to L1: on-chain identity, an agent marketplace, ZK proof-of-human, per the three-phase
  roadmap in `working-with-jarred.md`.
- Belief mapping / belief-indexed content strategy: a recurring, cross-client methodology
  (Anchorage, Avalanche, Midnight, RoboStrategy, SustainChain, AI Collective) that multiple
  Opportunity Brain briefs describe as converging with Mima/Trust Origin on the same "KYA"
  (know-your-agent) / proof-of-humanity thesis.
- Underlying data assets inherited from the retired MyLife/MyLife v2 prototype: a mempalace
  knowledge graph (16,000+ entities, 22,000+ triples) and a voice corpus
  (`~/.hermes-comms/training-data/voice-master.md`, 17,690 communications). These persisted past
  MyLife's 2026-05-19 retirement and carry forward as Mima's data foundation.
- Positioned inside an emerging market category described in the Opportunity Brain briefs as
  "KYA" / proof-of-humanity / ERC-8004 (an actual Ethereum agent-identity standard), alongside two
  adjacent projects Jarred tracks as analogues: Boop (Nethermind palm-scan ZK proof-of-humanity)
  and Ribbit "Tibber."

## Evolution timeline (March through July 2026)

- 2026-03-09: `memory/2026-03-09.md` already treats Mima/Trust Origin as an established
  commercial concept, explicitly separate from Jarred's "EXTINCTION" book project. David Deutsch
  is named as the key philosophical adversary (he calls alignment-by-constraint "slavery"), with
  the counter-framing already fixed: "Mima doesn't shackle AI, it verifies HUMAN AUTHORIZATION."
- 2026-03-17: `priority-stack.md` is created and ranks Project X / Mima as "the big bet," #2 in
  Jarred's business ranking, noting Ethereum Foundation (Tomas) interest.
- 2026-03-27: `memory/2026-03-27.md` documents "Belief Cluster Map v6," adding Sreeram Kannan
  (EigenLayer/EigenCloud founder) as a belief-system ally specifically because "EigenCloud is the
  verifiable trust layer that makes Mima/Trust Origin architecturally possible at scale." The same
  file logs an unsolicited third party in an unrelated meeting independently describing the same
  belief-alignment ecosystem concept, read by Jarred's team as validation.
- 2026-04-09: `meetings/2026-04-09-caa-winn-solutions-intro-tom-capone.md` records Tom Capone
  (CAA) discussing "Mima memory model concepts" alongside Jarred's Obsidian knowledge graph and
  CAA's digital twin infrastructure. Tom compares the work to Delphi, a well-funded mind-mapping
  startup.
- 2026-04-22: `memory/2026-04-22.md` flags crypto advisor Pat Yiu as a "heavy dogfood candidate
  for OpenClaw/Mima expansion" given he advises 6-7 crypto founders.
- 2026-04-30: `working-with-jarred.md` is compiled as the "foundational operating manual," fixing
  Mima's status as "vision active," the three-phase roadmap, and the hard rule against public
  mention on Winn.solutions.
- 2026-05-19: `memory/2026-05-19.md` records the retirement of MyLife/MyLife v2, Mima's prototype
  predecessor. Four launchd jobs are archived. `working-with-jarred.md` is updated same day to
  mark mylife "[ARCHIVED 2026-05-19]" and to state "mima reframed as active product line...mima
  continues independently as the active product line," carrying forward MyLife's data assets.
- 2026-06-10: `meetings/prep/2026-06-10-anchorage-vc-intro-prep.md` ranks Mima as the lead,
  highest-priority pitch angle for an upcoming Anchorage VC intro call, with a scripted one-liner
  ready to use.
- 2026-06-11: the fullest single validation event in the corpus. In
  `meetings/2026-06-11-ai-relationship-intelligence-platform-and-humanity-preservat-45d9150b.md`,
  Jarred spends 280 minutes in person in San Francisco with a person logged as "unknown-1." Cross
  referencing CRM files `crm/interactions/chappie.md` and `crm/interactions/chappy.md` against the
  exact date and description resolves this person as Chappie (also spelled Chappy), founder of
  the AI Collective, a 250,000-plus member global 501(c)(3) nonprofit spanning 50-plus countries.
  Jarred shares the Mima prototype concept and belief-index system as a potential integration
  reference for Chappie's platform. Chappie stresses the on-device, open-source requirement.
  Chappie also asks Jarred whether he has considered a mainstream front-end visualization for the
  relationship-intelligence platform.
- 2026-06-16 through 2026-06-19: daily memory logs and Opportunity Brain briefs
  (`opportunities/2026-06-12.md` through `2026-06-20.md`) repeatedly connect Mima/Trust Origin to
  Chappy's relationship-intelligence CRM, Boop (palm-scan ZK proof-of-humanity, wanted by
  Anchorage VC contact Matt Round), Anchorage's "agentic banking" framing, RoboStrategy, and
  Ribbit "Tibber" (from a 2026-06-18 Anchorage sync), all described as converging on the same
  proof-of-humanity thesis. `memory/2026-06-16.md` also instructs caution in an unrelated
  discovery call: "don't volunteer mima cap table, EF, GM, or TJ/Midnight intros." A
  2026-06-17 note flags an unresolved possible alias, "Mima Forge," tied to an unidentified
  DocuSign MNDA counterparty, explicitly marked "unclear" in the source itself.
- 2026-06-30: `meetings/2026-06-30-nick-metzler-introductory-meeting.md` records Jarred's
  introductory call with Nick Metzler. Jarred demos his personal automation stack (status bar,
  OAuth rotation cycle, dream cycle, Guardian/Doctor/Sage agents, priority queuing/focus mode,
  meeting ingestion wizard). This stack is OpenClaw-branded material; the word Mima does not
  appear anywhere in this meeting note or its raw transcript. The two instead begin discussing
  gamifying AI adoption inside enterprises.
- 2026-07-01 through 2026-07-06: daily memory logs and opportunity briefs show zero further Mima
  mentions. The Metzler thread (not yet named Recurro) develops in parallel, including a round 2
  call on 2026-07-02.
- 2026-07-07: `meetings/prep/2026-07-07-allan-upexi-ai-sync-prep.md` lists, as the lower-priority
  of two hypotheses for the next day's Allan Marshall (Upexi) sync, "a personal AI tool walkthrough
  (Claude Code, Fieldy-style capture, Mima/Personal AI concept)," described as lower marginal
  value but relationship-cementing. The higher-priority hypothesis in the same document is Allan
  wanting a concrete Upexi-branded AI/agent business surface, with no mention of Mima there. This
  document does not mention Metzler, Razink, Recurro, or an Agent OS concept anywhere.
- 2026-07-08 (today): two new meetings crystallize a separate concept. At 18:00 UTC,
  `meetings/2026-07-08-jarred-nick-metzler-carter-razink-ai-gamification-enterprise.md` records
  Carter Razink joining Jarred and Nick Metzler to explore gamifying AI adoption inside
  organizations. At 18:21 UTC,
  `meetings/2026-07-08-agentic-org-os-rsi-for-orgs-jarred-carter-nick-strategy-call.md` records
  the concept crystallizing into an "Agent Operating System" / recursively self-improving
  productivity platform for businesses, with the working name candidate "Recurro" (credited in
  the note as "Carter's AI-suggested name for recursive self-improvement for orgs"). Jarred plans
  to pitch Allan Marshall (Upexi) for a 10 to 50 million dollar seed. Neither 2026-07-08 meeting
  note, nor their raw otter/recall transcripts, nor the day's Opportunity Brain brief (generated
  14:16 UTC, before these meetings), mentions Mima at all.

## How Mima is pitched to clients and VCs

To venture investors, Mima is led with directly. The 2026-06-10 Anchorage VC intro prep document
ranks it first among available angles: "Mima / Project X - consumer Personal AI, agentic
triaging, ZK-proof human verification ('Trust Origin'), path to L1. Prototype exists. Ethereum
Foundation (Tomas / Leo Sprueth) interested. This is the asymmetric bet and the most 'VC-shaped'
thing in your portfolio. Lead with this if they're open to it." The prepared one-liner: "Mima is
a consumer Personal AI that triages your life and proves you're human without surrendering
identity. ZK-proof Trust Origin layer. Path to L1." The same document instructs Jarred not to make
a hard ask in the intro call itself, but to offer a 30-minute Mima technical deep dive if pushed,
and to log interest to a `deals/` folder afterward. No `deals/mima` or `deals/anchorage-vc`
subfolder actually exists in the workspace today, so that follow-through step is unconfirmed.

To a potential consumer-layer ally (Chappie, 2026-06-11), Mima is shared organically during a
long relationship-building conversation rather than pitched formally, with emphasis on shared
philosophy (preserving individuality and humanity against AI-driven homogenization) rather than a
sales ask.

To cold or unknown new contacts, Mima is one of exactly five named active business areas Jarred is
pattern-matched against. The 2026-06-30 win-win introductions prep document instructs: "Pattern-
match against Jarred's 5 active areas (WV agent execution, Mima, WCI/Upexi/Dr. Williams/Anchorage
client work, GM ops, Sacramento SMB AI / Folsom rush)."

To Allan Marshall specifically, Mima is treated as a soft, low-priority, relationship-cementing
side-topic rather than a business ask, explicitly ranked below the possibility that Allan wants a
concrete Upexi-branded AI business (2026-07-07 prep document).

Internally, `CORE_MEMORY.md` frames Mima plainly as "Secondary priority to Winn.ventures" with
named key people Matthew James and Rohan (mima.ai) attached, and logs the Ethereum Foundation
relationship (Tomas Stancak) as "organic conversation, not formal pitch."

Mima is never pitched publicly. The hard rule in `working-with-jarred.md` states Winn.solutions
content scoping "never references openclaw or mima," limiting the public site to three anonymized
case studies, and lists "mentioning openclaw/mima on winn.solutions" among banned behaviors.

## Relationship to the Agent OS concept and to Fieldy-style capture

No document anywhere in the mini's workspace draws an explicit connection between Mima and the
Agent OS / RSI-for-orgs / Recurro concept. This was checked multiple ways: the synthesized meeting
notes for all three Metzler/Razink meetings (2026-06-30, and both meetings on 2026-07-08), the raw
otter and recall transcripts behind those same meetings, every daily memory log from 2026-07-01
through 2026-07-08, and every Opportunity Brain cross-meeting-connection brief in the same window,
including the one generated the afternoon of 2026-07-08 itself. None contain the word Mima. This
is a meaningful negative result precisely because the Opportunity Brain briefs are designed to
surface exactly this kind of cross-thread connection, and did so repeatedly for Mima's links to
Chappy, Boop, Anchorage, and RoboStrategy throughout June, yet never once linked Mima to the
Metzler/Razink thread.

Agent OS / Recurro is, on the evidence, a separately originated concept. It began 2026-06-30 as an
intro call with Nick Metzler that started as a catch-up about gaming, tokenomics, and the web3-to-
web2 shift, and only turned toward gamifying enterprise AI adoption partway through. Carter Razink
joined 2026-07-08, bringing a physics and engineering background and a case study (a 4-person team
producing 16x baseline output versus a control group of 18 at 2.5x). The concept crystallized that
same day into an "Agent Operating System" aimed at businesses, not individual consumers, with a
core mechanic of gamifying AI adoption (leaderboards, token-burn-to-output ratios, OKRs tied to
weighted subtasks) rather than personal triage or identity verification. Its first pilot user and
investor target is explicitly Allan Marshall (Upexi), for a planned 10 to 50 million dollar seed
raise, per the 2026-07-08 strategy call note.

Two indirect points of contact are worth naming, both flagged here as this author's own synthesis
across the corpus rather than a connection stated anywhere in Jarred's own notes:

First, a shared philosophical core. The humanity-preservation thesis that anchors Mima, in
Jarred's own words from the 2026-06-11 Chappie meeting ("I don't want everybody turning into
bots... That's literally the preservation of humanity is the thing that I really care most
about"), is echoed almost exactly in the 2026-07-08 gamification meeting's key quotes: "I want you
to maintain your unique sense of individuality - as AI is adopted and we're all influenced by it,
we lose our unique sense of individuality and humanity." Same author, same underlying belief,
applied to two different product surfaces: personal AI for Mima, enterprise AI adoption for Agent
OS.

Second, a shared target investor on a tight timeline. Allan Marshall (Upexi) was slated, in the
2026-07-07 prep document, for a lower-priority "Mima/Personal AI concept" walkthrough at a
recurring bi-weekly sync. Approximately 24 hours later, the 2026-07-08 strategy call set Allan as
the first pitch target for Agent OS/Recurro's seed round. The two threads appear to be converging
on the same person in the same week without being explicitly merged or cross-referenced anywhere
in Jarred's own notes.

On Fieldy specifically: Fieldy is Jarred's ambient wearable meeting-capture and Claude MCP
pipeline, and it is the infrastructure that produced essentially all of the source material read
for this dossier (every meeting note pulled is tagged fieldy, fieldy-extracted, otter-zapier,
recall, or granola, feeding the same CRM pipeline). The 2026-07-07 Allan prep document bundles
Fieldy-style capture together with Mima in the same breath, listing "Claude Code, Fieldy-style
capture, Mima/Personal AI concept" as three adjacent pieces of Jarred's personal AI tooling worth
walking Allan through, which suggests Fieldy is thought of as a capture-layer companion to Mima (or
a working proof of concept for what an ambient-triage layer under Mima might eventually look like)
rather than as a stated component of it. Agent OS's own capture mechanism, per the 2026-07-08
meetings, is instead built around a "meeting ingestion wizard" (part of the personal stack demoed
to Nick on 2026-06-30) plus ClickUp or Linear as the backbone. Fieldy is not named anywhere in the
Agent OS material.

## People associated

Associated with Mima specifically:
- Jarred Winn: creator and owner of the concept.
- Matthew James: tagged "(Mima)" in `priority-stack.md` and `CORE_MEMORY.md` as a Tier 1 contact.
  No fuller biography found anywhere in the corpus; under-documented.
- Rohan: tagged "(mima.ai)" in `CORE_MEMORY.md` and `priority-stack.md`. It is ambiguous from the
  source material whether mima.ai is a distinct company/domain Rohan is associated with, or the
  domain secured for Jarred's own product.
- Tomas / Tomasz K. Stanczak: Ethereum Foundation, Founder Success team. `crm/contacts.md` logs a
  next action to "draft outreach connecting Trust Origin architecture to his ERC-8004 work."
  Relationship logged as dinner-level and organic, not a formal pitch.
- Leo Sprueth: also Ethereum Foundation Founder Success team, introduced via Tomas.
- Sreeram Kannan: founder of EigenLayer/EigenCloud, added as a belief-system ally because
  EigenCloud is described as the trust layer that makes Trust Origin possible at scale.
- Chappie, also spelled Chappy: founder of the AI Collective, a 250,000-plus member global
  501(c)(3) nonprofit across 50-plus countries. Jarred's core Mima validation partner in the
  2026-06-11 meeting. Appears as "unknown-1" in the raw meeting note; identity resolved here via
  cross-reference against dated CRM interaction files.
- Tom Capone: CAA, compared Mima's memory-model concepts to the startup Delphi.
- Matt Round: Anchorage VC contact, interested in Boop, a project adjacent to Mima's KYA space.
- Kevin McCordic: RoboStrategy, subject of a note instructing caution around volunteering Mima
  details in an unrelated discovery call.
- David Deutsch: named as the key philosophical adversary to Mima's premise.
- Pat Yiu: crypto advisor flagged as an OpenClaw/Mima dogfood candidate.
- Jesse Phillips and Harry Lassige: Trustware, a possible agentic-commerce supplier relationship
  adjacent to Mima.

Associated with Agent OS / Recurro (for context, not part of Mima):
- Nick Metzler: game designer with a tokenomics and behavioral psychology background, an in-house
  tokenomics/governance role at Framework Ventures, and his own tokenomics research company.
- Carter Razink: physics and math academic background (a CERN track interrupted by COVID), serial
  founder with multiple exits, most recently CTO/CEO of a stablecoin-rewards spinout that exited.
  Appears in earlier, separate CRM records as "Carter (Spree)" from an existing bi-weekly sync
  relationship dating back to at least March 2026.
- Allan Marshall (Upexi CEO): shared target across both Mima's soft pitch (2026-07-07) and Agent
  OS's hard seed-round ask (2026-07-08).

## Exact quotes with source paths and dates

"My dream when I was first starting a business was I was like to have an executive assistant that
was as plugged into my priorities as I was. And to not miss an opportunity based on lack of
attention towards that." Jarred Winn, 2026-06-11,
`meetings/2026-06-11-ai-relationship-intelligence-platform-and-humanity-preservat-45d9150b.md`.

"I don't want everybody turning into bots. We're literally going to have all of our interactions
influenced by AI unless we're careful. That's literally the preservation of humanity is the thing
that I really care most about." Jarred Winn, 2026-06-11, same file as above.

"This has to be fully on device. This has to be, I think, fully open source because this is
touching like all of your most private sensitive things." Chappie (logged as unknown-1),
2026-06-11, same file as above.

"Mima doesn't shackle AI, it verifies HUMAN AUTHORIZATION." Internal note, 2026-03-09,
`memory/2026-03-09.md`.

"Bridge: EigenCloud is the verifiable trust layer that makes Mima/Trust Origin architecturally
possible at scale." Internal note, 2026-03-27, `memory/2026-03-27.md`.

"Mima is a consumer Personal AI that triages your life and proves you're human without
surrendering identity. ZK-proof Trust Origin layer. Path to L1." Prep talking point, dated
2026-06-10, `meetings/prep/2026-06-10-anchorage-vc-intro-prep.md`.

"Mima is the asymmetric bet and the most VC-shaped thing in the portfolio, lead with it if they're
open to it." Gbrain take, weight 0.72, same file as above.

"He wants an AI onboarding for himself, a personal AI tool walkthrough (Claude Code, Fieldy-style
capture, Mima/Personal AI concept). Lower marginal value but relationship-cementing." Prep note,
dated 2026-07-06 for a 2026-07-07 meeting, `meetings/prep/2026-07-07-allan-upexi-ai-sync-prep.md`.

"Working name candidate: 'Recurro' (Carter's AI-suggested name for recursive self-improvement for
orgs)." Decision log, 2026-07-08,
`meetings/2026-07-08-agentic-org-os-rsi-for-orgs-jarred-carter-nick-strategy-call.md`.

"I want you to maintain your unique sense of individuality - as AI is adopted and we're all
influenced by it, we lose our unique sense of individuality and humanity." Jarred Winn, 2026-07-08,
`meetings/2026-07-08-jarred-nick-metzler-carter-razink-ai-gamification-enterprise.md`.

"My team of four is currently producing 16x baseline; the control group of 18 is at 2.5x." Carter
Razink, 2026-07-08, `meetings/2026-07-08-agentic-org-os-rsi-for-orgs-jarred-carter-nick-strategy-call.md`.

"mima continues independently as the active product line." Internal note, 2026-05-19,
`memory/2026-05-19.md`, describing the retirement of MyLife/MyLife v2.

## Confidence notes

High confidence: Mima's definition, its three-phase roadmap, the Trust Origin architecture, its
lineage from the retired MyLife/MyLife v2 prototype, and its internal-only public-facing status are
all corroborated across at least five independent documents (`priority-stack.md`,
`working-with-jarred.md`, `CORE_MEMORY.md`, the 2026-06-10 Anchorage prep, and the 2026-06-11
Chappie meeting).

High confidence: no explicit connection between Mima and Agent OS / Recurro exists anywhere in the
mini's workspace as of 2026-07-08. This was checked across synthesized meeting notes, raw
transcripts, daily memory logs, and cross-meeting Opportunity Brain briefs, and confirmed absent
in all of them. The two overlaps described in this dossier (shared philosophical core, shared
target investor on a tight timeline) are this author's own inference from reading both threads
side by side, not a stated connection in any single source document, and should be treated
accordingly if relayed as fact.

Medium confidence: "unknown-1" in the 2026-06-11 meeting is Chappie/Chappy. This is resolved via
cross-referencing CRM interaction files against exact dates and descriptions (San Francisco,
several hours, a 250,000-member collective), which line up precisely, but there is no direct
name-stated-in-transcript confirmation.

Low confidence, unresolved: "Mima Forge," an alias flagged on 2026-06-17 and tied to an
unidentified DocuSign MNDA counterparty. The source note itself calls this "unclear," and no
further resolution was found.

Low confidence, under-documented: Matthew James and Rohan (mima.ai) as people or entities. No
fuller biography, company detail, or additional context was found anywhere in the searched corpus
beyond their tags in `priority-stack.md` and `CORE_MEMORY.md`.

Procedural notes: the `~/.openclaw/workspace/knowledge` directory referenced in the sweep
instructions does not exist on the mini, confirmed via direct listing; that portion of the method
legitimately returns nothing. No dedicated file or folder named for Mima, Trust Origin, or Project
X exists anywhere in the workspace; a filename search returns only unrelated substring
false-positives (for example PalmImagePlugin.py). No ASR-variant aliases (MIMA, Mema, mimma) were
found anywhere in the searched files. No `deals/mima` or `deals/anchorage-vc` subfolder exists
despite the 2026-06-10 prep document's instruction to create one if interest was expressed, which
is an open, unconfirmed gap rather than evidence either way. This dossier reflects only what exists
in Jarred's own operational CRM and memory record on the mini as of 2026-07-08; several entries
(Opportunity Brain briefs, meeting-prep files) are AI-generated syntheses rather than Jarred's own
verbatim words, though the quotes section above is verbatim transcript excerpt in each case.
