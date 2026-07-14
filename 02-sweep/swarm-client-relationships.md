# Client Relationships as a Product Surface: Synthesis Dossier

Swarm topic: client-relationships (client portals, client-facing views, feedback loops, CRM-like features, consulting delivery). Compiled 2026-07-08 from six reader passes plus a direct read of the primary tracking thread and two sibling swarm dossiers (used only to resolve one contradiction, per instructions, not to re-run the search).

## Headline

There is no single, named, unified "client relationships" product anywhere in the estate. What exists instead is a large, fragmented stack of CRM-like infrastructure (contact/interaction tracking, relationship-decay scoring, pre-meeting briefings, per-client review consoles) built for Jarred's own consulting delivery, plus one explicit strategic claim from today's (2026-07-08) Agent OS founding call that relationships themselves, not technology, are the moat of the whole new product concept ("Moat: trust, relationships, speed... nothing stops Salesforce/ClickUp from copying"). The most concrete, load-bearing fact for the downstream overview is that an existing Winn.solutions consulting client, Allan Marshall (CEO of Upexi), is simultaneously the target first pilot and investor ($10 to 50M) for the new, still-unnamed Agent OS product, confirmed directly in the 2026-07-08 tracking thread. Every reader pass that looked for a literal "client portal," dedicated client-facing view, or unified CRM product came back negative: none exists as a built or even mocked-up artifact. Two identity questions remain genuinely open and matter to how "Fieldy and Recall" and "client relationships" connect: whether today's Nick Metzler is the same "Nick" as a 2026-06-25 CRM entry for "Nick from Recall.ai," and whether the goal context's framing of today's call as being "with Nick and Carter of Fieldy/Recall" is accurate at all (evidence points instead to Fieldy and Recall being Jarred's own capture infrastructure that recorded the call, not a company Nick/Carter represent).

## What exists / was built

Built and operating (not just proposed):

- **Fieldy-to-CRM sync.** `fieldy-crm-sync.py`, decided 2026-06-01 (fieldy-clawdia decision 0006), runs on a 600-second cron on mini. Gates every write through an LLM pass (not keyword heuristics) so it does not log Jarred, family, or unidentified speakers as clients, and resolves commitment direction per contact (asks_outbound = Jarred owes them). Backfill took contacts.md from 80 to 90 entries.
- **10-step meeting-ingest pipeline**, documented in `/Users/jarredwinn/Projects/brain/docs/architecture.md` (repo created 2026-06-16). Step 1 is "CRM contact resolution + interaction creation," writing to `crm/contact-aliases.json` (fieldy-clawdia) and `crm/contacts.md` (Fieldy-native), reconciled nightly at 2am PT.
- **Clawdia's own CRM**, one of her four named core functions per `/Users/jarredwinn/Projects/clawdia-atlas/docs/00-overview.md` (verified 2026-06-15): she owns the `crm/` markdown files, a "first-contact rule" creates an entry for every new person, and reach-out drafts are staged for approval, never auto-sent.
- **"Lobster pipeline"** (clawdia-atlas `docs/06-processes-and-crons.md`, verified 2026-06-15): auto-generates a 7-section client/contact briefing (CRM snapshot, recent activity, value prop, red flags, conversation starters, desired outcome, research links) 24 hours before a scheduled meeting, delivered 1 hour before.
- **`person-context.py`**: a unified lookup tool (clawdia-atlas `docs/04-tooling.md`) that runs CRM, MemPalace, interactions, follow-ups, and email lookups in parallel and is mandatory before drafting anything about a contact. Functionally a backend "360 client view" API with no front end yet.
- **MemPalace `crm` wing**: roughly 1,989 entities and 856 triples as of 2026-06-15, one of four wings (memory/crm/gm/training_data) in Clawdia's episodic knowledge graph.
- **A relationship-health scoring and decay stack on mini** (`~/.openclaw/workspace/scripts/`, undated but currently present): `crm-decay-alert.py`, `crm-decay-scorer.py`, `crm-staleness-watch.py`, `crm-cache.py`, `crm-followup-prep.py`, `crm-automation.py`, `hubspot-crm.py`, `hubspot-sync-contacts.py`, `mempalace-crm-unify.py`. `crm-automation.py` documentation states it addresses "39 overdue follow-ups manually tracked, saving 3-6 hours/week."
- **An earlier, hand-built personal CRM** predating all of the above: `anchorage-workspace/99-source/archive-snapshots/friction-anchorage-original-20260419-151127/media/clients.md` and `pipeline.md` (created 2026-03-17/18, archived 2026-04-19). Already had a quantitative relationship-decay formula (`current_strength = relationship_strength * (0.97 ^ (days_since_last_contact / 7))`, auto-reach-out below 2.0 or after 21+ days) and a formal sales-pipeline schema (Prospect/Stage/Value/Next Action).
- **`relationship-map.md`** (`anchorage-workspace/00-orientation/`, snapshot 2026-04-27): a hand-built ASCII relationship graph with per-contact trust scores (0 to 10, with trend arrows), an introduction graph (who introduced whom), and a "who knows what" information-flow matrix per deal track.
- **Anchorage feedback loop, channel one**: `anchorage-agentic-preview/review/REGENERATE.md` (2026-06-23). Reviewers click any element on the live deck, leave a comment, export to GitHub issues in `anchorage-deck-feedback` (labels feedback/accepted/denied/applied), Jarred triages (2 clicks each), and the deck regenerates from a single source of truth. Described as internal-team-only today.
- **Anchorage feedback loop, channel two**: `anchorage-agentic-preview/versions/ingest-feedback.sh`. Marker.io screenshot annotation on the deck also files private GitHub issues; applying an edit auto-snapshots a version and syncs the Marker item back to Done.
- **anchorage-review-console** (`INTENT.md` authored 2026-06-22, repo present since 2026-06-18): a single-file localhost HTML console listing every Anchorage GTM artifact for inline review, with per-item localStorage feedback and markdown export. Explicitly internal-only, not deployed to the client. Its own INTENT.md stages an explicit roadmap: step 1 local single-file console (done) to step 2 server-side feedback service, step 3 session resume/fork (resuming the live agent that produced an item), step 4 in-document review, with the console's own text noting it "genuinely becomes a client-facing surface handed to Anchorage" only if a later step lands.
- **claudecode-bar `/rq` review queue** (`main.swift`, `reviewQueueRows()` around lines 2360 to 2400, commit 866068a, 2026-06-26): a menu-bar popover surfacing a Google-Drive-hosted `QUEUE.md`, grouped by client, showing items pending Jarred's sign-off with priority and age. The closest built per-client organizational feature in the actively developed GUI. `docs/recall-docs-panel-plan.md` (same date) has an explicit open question on how to formally model "client" as a grouping concept, noting it is not yet resolved.
- **Org-to-client-to-project-to-document hierarchy**, physically real in Google Drive via the `/newclient` and `/newproject` skills. `knowledge/INDEX.md` (last updated 2026-07-05) lists the canonical scaffold (00_PROFILE/01_ENGAGEMENT/02_DELIVERABLES/03_COMMS/04_FINANCIALS/memory-bank) populated for Anchorage (Nathan McCauley), Upexi (Allan Marshall), CoinGecko (TM Lee, Bobby Ong), Shinzo (empty), 0G (empty), Internal, Winn.Solutions, and 67 archived former clients.
- **client-style-guides repo**: an editing workbench for 7 clients' Personal Style Guides (PSGs), with `bin/promote.sh` pushing to a belief-field-platform serving slot (`org/objective-ledger.yaml`, snapshot 2026-07-02). Scaffolded and seeded; no editing session logged yet.
- **Allan Marshall's content approval chain**: a documented, real workflow (`knowledge/3-resources/people/allan-marshall.md`, last reviewed 2026-06-02) where ghostwritten drafts pass Jarred first, then a Brian Rudick editorial gate, then Allan, driven by a secret voice-guide gist (`ef9252dcbe4eb8620d708e3d04d40177`).
- **client-feedback skill and registries** (referenced from `anchorage-workspace/Nathan McCauley/.../feedback-ledger.md` and `feedback-audit-2026-07-07.md`, 2026-07-07): standing client feedback compiled into a persistent rules registry (`~/.claude/skills/client-feedback/registries/anchorage.json`, not directly opened by any reader) that mechanically gates future content generation, e.g. a hard fail on the word "plumbing" in Anchorage content and a warn on tired-infrastructure metaphors.
- **ClickUp per-client action-item design** (`miscellaneous/threads/2026-06-17-clickup-ops-and-action-item-system.md`, status graduation-candidate): explicit design for a tracker that is per-client as well as per-employee, with client-facing items routed through Jarred rather than pinged directly the way employee items are.
- **Growing Mindfully's Kindred portal** (`kindred.growingmindfully.org`, referenced in `knowledge/REPO-PORTFOLIO.md`): a live, deployed parent-facing portal in a different Winn-adjacent business line. Real working portal UX precedent, not a Winn Solutions consulting-client artifact.

Adjacent, explicitly out-of-scope material (see Grey areas below for why it is flagged rather than folded in):

- **mima** (concept authored February 2026, PDF exported 2026-07-07 to `/private/tmp/mima_story_v3.pdf`): lists "client management" as one of its core liaison functions ("Business emails. Personal texts. Social media engagement. Scheduling. Follow-ups. Client management. mima is your liaison for all of life") and names "the freelancer managing clients across five platforms" as a target persona. Its Approve/Edit/Skip triage-card loop (draft, human approves/edits/skips, every action trains the model) is the clearest reusable pattern in the whole corpus for a general client-feedback loop. Its Phase 2 roadmap sketches a relationship knowledge graph with "relationship health" scoring ("You haven't reached out to Marcus in 3 weeks"), not yet built. **Per Jarred's direct, authoritative correction on 2026-07-08 (see Grey areas), mima is unrelated to the Agent OS product concept and must be excluded from it.** It is retained here only as adjacent prior art and a source of reusable patterns, not as a component of the product being consolidated.
- **allan-ai-deck** (`miscellaneous/allan-ai-deck/deck.html`, v12 as of 2026-07-07): a teaching deck built for Allan Marshall containing a demo slide that applies the mima Approve/Edit/Skip pattern to an external commercial relationship (a vendor invoice follow-up: "Following up on invoice #2291, is this approved on your end?" drafted reply "Approved on our side. Payment lands Friday per net-30."). Per the sibling swarm-gui.md and swarm-allan-marshall.md dossiers (cross-checked directly in this pass), this deck is explicitly educational, not a product pitch, contains no Nick/Carter names, and predates the 2026-07-08 Agent OS conversation. It belongs to Jarred's standing Winn.solutions ghostwriting/advisory engagement for Upexi, a separate relationship track from the new pilot pitch (see People section).
- **executive-agent-gui "executive briefing surface"** (born 2026-07-03, per `executive-agent-gui/memory-bank/2026-07-03-birth-thread.md` and `research/vision-brief.md`): a decided product direction, not client-specific by name, that distills session transcripts to decisions, questions, and milestones for a non-technical audience. The vision-brief explicitly frames this as a candidate client-experience layer: "A calm executive briefing surface is precisely a client-experience layer over AI work. That makes executive-agent-gui a candidate component of the enterprise pitch, the face the client's leadership sees" (vision-brief.md, lines 96-100, compiled 2026-07-03). This is the closest prior art in shape to a future client-facing portal, even though nothing found labels it "client-facing" outright yet.

Confirmed to have nothing on this topic (checked and ruled out, useful for scoping):

- **command-center** (`CLAUDE.md`, last commit 2026-06-17, status TABLED): purely an internal notification-triage cockpit for concurrent Claude Code sessions. No client-facing surface, no CRM, no client-feedback concept anywhere in the repo.
- **teamclaude-fleet** (`INTENT.md`): every "client" occurrence is the technical/HTTP sense (API client of a rotation proxy), never a business client. Pure backend substrate.
- **miscellaneous/DEBRIEF.md** (2026-07-03): entirely about an unrelated "Agent Browser Viewer" tool; zero client-relationship content.

## Key features

Concrete, named capabilities that exist today or are explicitly specified:

1. CRM contact resolution, interaction logging, and follow-up tracking, LLM-gated to avoid misclassifying family or unidentified speakers as clients (fieldy-crm-sync.py, brain pipeline step 1).
2. Relationship-decay scoring with an auto-reach-out trigger, both in an early hand-built form (2026-03-17/18 formula) and as a running mini script stack (`crm-decay-alert.py`, `crm-decay-scorer.py`, `crm-staleness-watch.py`).
3. Automated pre-meeting client/contact briefings (Lobster pipeline: CRM snapshot, recent activity, value prop, red flags, conversation starters, desired outcome, research links, delivered 1 hour ahead).
4. A unified "360 view" lookup (`person-context.py`) combining CRM, MemPalace, interactions, follow-ups, and email before any contact-related drafting.
5. Per-client review and feedback loops for deliverables, in two working forms for Anchorage (GitHub-issues-via-click-to-comment, and Marker.io screenshot annotation), plus an internal-only staged console (anchorage-review-console) with a roadmap toward server-side feedback and session resume.
6. A menu-bar review queue grouped by client (claudecode-bar `/rq`), surfacing what is pending Jarred's sign-off with priority and age.
7. A formal, scaffolded per-client Drive hierarchy (PROFILE/ENGAGEMENT/DELIVERABLES/COMMS/FINANCIALS) instantiated via `/newclient`, already populated for at least 6 active or dormant clients plus 67 archived ones.
8. Per-client voice/style matching for ghostwritten content (client-style-guides workbench, 7 clients; Allan Marshall's specific approval chain of Jarred to Brian Rudick to Allan).
9. A mechanical, registry-driven content-quality gate keyed to standing client feedback (the client-feedback skill's per-client registries, e.g. anchorage.json banning specific tired language).
10. A design decision, stated explicitly for Anchorage, to let the client give feedback in tools they already use (Google Docs comments, a spreadsheet) rather than building a bespoke portal: "Comment / give feedback in their own tools (Google Docs in comment mode, a spreadsheet 'so Kate can comment')" (`anchorage-agentic-preview/INTENT.md`, authored 2026-06-22).
11. A governance rule separating client-facing communication from internal employee communication: client-facing items route through Jarred; employee items are pinged directly (ClickUp design thread, 2026-06-17).

## Must-haves

Things stated, explicitly or by strong operational precedent, as non-negotiable for anything touching client relationships:

- **Client experience must not degrade.** This is the single stated constraint from Anchorage's CEO on the entire equity-for-AI-overhaul pilot: "sole constraint: client experience" (Nick Metzler call, 2026-06-30, digested 2026-07-01, collated in `executive-agent-gui/research/raw/collation-2026-07-03.md`, line 178).
- **No uninvited or undisclosed meeting-capture bots in client meetings.** Established as a hard rule after a live incident: an unnamed "Winn.ai" notetaker bot was confirmed joining a live Anchorage Digital weekly sync on 2026-07-07, prompting a full remediation purge (Google OAuth revoked on 16 apps, 7 Zoom Marketplace apps removed, Zoom AI auto-start disabled). A client had already complained about this exact class of intrusion on 2026-06-30 ("F***ing Winn AI keeps following me").
- **Quote and fact provenance verification before shipping any client-facing deliverable.** Standing macro lesson (2026-06-18): "Verify every quote in a client-facing deliverable is an exact substring of its real source... a render/visual pass is not a truth check."
- **Confirm output format and delivery channel up front before drafting for a client.** Standing lesson from a real incident (2026-06-25, a CDSS legal document task): failing to do this drove roughly 8 rounds of rework.
- **Client onboarding intake must capture constraints before any client-facing deliverable is authored**: review surface, approval flow, red lines, no-fly list, spokesperson map, past failures, ops lead times, provenance, and call length, formalized in the `/newclient` skill (audited 2026-06-18).
- **CRM writes must be single-writer gated.** Since a 2026-04-16 "agent cull," only main/Clawdia writes to `crm/` files; all other agents only read. Precedent for how any future client-relationship product should govern its own data.
- **Sensitive client-specific information must be excluded from every export.** `brain/docs/belief-system.md`: client-specific sensitive beliefs are explicitly excluded from all exports, distinct from the public belief-field.

## Grey areas + open questions

- **The mima/Agent-OS boundary.** Jarred issued a direct, authoritative correction on 2026-07-08 (read directly in this pass from `threads/2026-07-08-agent-os-product-concept-consolidation.md`, lines 26-28): "Mima and Agent OS are completely unrelated... EXCLUDE from the Agent OS product concept, keep only as an explicit out-of-scope note so no one re-conflates them." This directly contradicts the framing in this swarm's own goal context, which lists "something called mima" as one of the six things being consolidated into one product. This dossier follows the more recent, more authoritative correction: mima's client-management content is presented above as adjacent prior art, not as part of the product. Any downstream overview should do the same.
- **"Recurro" is not the product's name.** Same correction: "Recurro is Carter's concept for agentic engineering (his recursive-self-improvement framework for engineering orgs), NOT the product's working name. The joint product is currently unnamed." Several meeting-note artifacts (per reader findings, not directly verified in this pass) call Recurro a "working name candidate" for the joint product; Jarred's correction states this is wrong.
- **Is today's "Nick" the same Nick as the 2026-06-25 Recall.ai contact?** Mini's `crm/interactions/nick.md` merges a 2026-06-25 entry ("Nick from Recall.ai gave a brief live demo of their desktop SDK... real-time meeting transcript capture from Zoom") with 2026-07-08 entries for Nick Metzler ("game designer and gamification expert... nick@winwin.game"). No reader pass found a cross-reference tying today's Nick Metzler to Recall.ai; this reads as a first-name-only contact-matching conflation, not a confirmed dual affiliation. This matters directly to the goal context's framing of today's call as being "with Nick and Carter of Fieldy/Recall": the stronger-supported reading is that Fieldy and Recall are Jarred's own meeting-capture infrastructure (Fieldy an ambient/wearable pipeline, "Recall" a Recall.ai-SDK-based bot Jarred built, repo `recall-notetaker`) that recorded today's call, not a company Nick or Carter represent. Unresolved; recommend confirming directly with Jarred.
- **Two different "Carters" exist in the data.** Carter Razink (today's 2026-07-08 call: physics/math background, serial founder, ex-stablecoin-rewards CTO, carter@raz.ink) is a different person from a "Carter" referenced in an unrelated 2026-06-09 automation-program thread, independently verified via `github.com/Winnsolutionsadmin/skills-registry/_meta/program-log.md` as "the Spree to travel-tech AI eng leader" (from a 2026-06-05 meeting). Confirmed distinct; flagged so future synthesis does not merge them.
- **"Alan" and "Allan Marshall" are confirmed to be the same person.** Two sibling swarm dossiers (swarm-gui.md and swarm-allan-marshall.md, both cross-checked directly in this pass) flag this as an open, unconfirmed inference, citing a spelling mismatch between "Alan" (in the 2026-07-08 call notes, target pilot/investor) and "Allan Marshall" (the Upexi CEO client who received the teaching deck). Reading the primary tracking thread directly resolves this: `threads/2026-07-08-agent-os-product-concept-consolidation.md` line 21 states plainly, "Alan/Allan (Upexi CEO, Allan Marshall) has $10-50M appetite; pitch end of this week or next (Alan meeting due ~7/17-18)." This is the same entity, written both ways by different note-takers. This is arguably the single most important client-relationship fact for the downstream overview: an existing consulting client relationship is the go-to-market wedge for the new, unnamed Agent OS product.
- **Will any internal review console ever go client-facing?** anchorage-review-console's own INTENT.md treats this as a live, undecided branch point ("it genuinely becomes a client-facing surface handed to Anchorage, or step 2's server-side feedback lands"), not a committed roadmap item.
- **ws-retain and ws-deepen are named goals with zero supporting work.** `the-sage/goals/goals.json` (objective id "ws," updated 2026-06-22) lists these two drivers (renewal/retention/churn, and scope-expansion/upsell) with empty `repos: []`, versus `ws-deliver`, which has four repos attached (anchorage-review-console, anchorage-agentic-preview, anchorage-deck, upexi).
- **Client satisfaction health-check is defined but not instrumented.** Same goals.json: a green/yellow/red per-client health check is the stated KR and "truest retention leading-indicator," but the source annotation itself says "needs first check."
- **No literal client portal or CRM product was found anywhere.** Six independent reader passes, across roughly a dozen distinct corpora (executive-agent-gui, claudecode-bar, anchorage-workspace and its sibling repos, fieldy-clawdia, brain, knowledge, clawdia-atlas, miscellaneous threads and org ledgers, command-center, teamclaude-fleet, the-sage), all returned the same negative: no dedicated "client portal," "CRM" (as a named product), or client-facing-view mockup exists as a built or drafted artifact. What exists is CRM-like infrastructure serving Jarred's own workflow, not a product surface a client would ever see.
- **Open CRM data-quality bugs, unresolved as of 2026-07-01**: meeting-title mis-transcription pollutes CRM records (e.g. "Inkridge" for "Anchorage"), and the same call gets double-ingested into two separate CRM entries when both Otter and Recall capture it independently.
- **The "Clarify" rung of the contact/speaker-identification pipeline is unbuilt.** `brain/docs/architecture.md`: "No automated clarifying-question loop yet. Ambiguous speakers are resolved manually by Jarred. This is the missing rung." A related known sharp edge: meetings where Jarred is merely an observer flood the CRM with low-strength contacts; a "context-only" tag is proposed but not built.

## Value propositions

- **Relationships as the moat, stated explicitly for the whole new product.** From the 2026-07-08 call (read directly): "Moat: trust, relationships, speed (explicitly: nothing stops Salesforce/ClickUp from copying)." This reframes "client relationships" from a feature category to the core competitive-defensibility argument for the entire Agent OS concept.
- **Equity-for-overhaul framed around protecting client experience.** The Anchorage pilot pitch is a no-cash-cost AI-adoption overhaul paid in equity ("even 1% is $40M" on a $4B valuation, on top of an existing $25k/mo retainer), explicitly gated on preserving client experience, with the CEO reportedly receptive ("what would you pay?", "a lot").
- **Reduced relationship-management overhead for consulting delivery.** `crm-automation.py` documentation cites "39 overdue follow-ups manually tracked, saving 3-6 hours/week" as the addressed problem.
- **Churn prevention as an explicit cost-of-inaction argument.** An "engagement watchdog" concept (ranked #4 of 8 ideas from the 2026-06-30 conversation, per the 2026-07-01 digest) is justified directly: "we've lost more clients to that than anything else."
- **Voice-matched content at scale.** Per-client Personal Style Guides (7 clients onboarded) let ghostwritten and generated content match each client's voice without a bespoke process per engagement.
- **Client work is the org's real-revenue bucket.** `org/README.md` (2026-07-02): 18 of 126 tracked repos are tagged "winn, client_work," described as "real revenue (Anchorage, Upexi, CoinGecko)." This grounds why the client-relationship surface matters commercially and is not merely an internal ops nicety.
- **A concrete internal case study as the product's own proof point.** Carter's cited 4-engineer team at 16x baseline versus an 18-engineer control team at 2.5x is explicitly being packaged as a client-facing/investor-facing proof point (see Goals below), i.e., the product's own delivery relationship (with Carter's team) becomes marketing collateral for future client relationships.

## Goals (short-term / long-term)

Short-term, directly from the 2026-07-08 call and its immediate follow-ups:

- Concept doc and early deck with branch scenarios owed by Jarred, due 7/15.
- Shared three-way doc (Jarred, Nick, Carter) due 7/11.
- Meet Allan Marshall (Upexi), 7/17-18, pitching $10 to 50M.
- Carter owes: a Recurro doc (7/10), a matrix.build GUI-inspiration link (7/9), and the packaged 16x case study (7/15), the concrete client-facing proof point referenced above.
- Nick owes: a gamification mechanics definition (7/31).
- P0 for Jarred the same day (2026-07-08): ping Nick and Carter individually with availability.
- Client satisfaction health check (green/yellow/red) needs its "first check" instrumented; no date attached in the source.

Long-term, from formal org-level goal tracking:

- **"Deliver & retain Winn.solutions clients"** is a named North Star (`the-sage/goals/goals.json`, objective id "ws," updated 2026-06-22), with three drivers: `ws-deliver` (populated: anchorage-review-console, anchorage-agentic-preview, anchorage-deck, upexi), `ws-retain` (renewal/retention/churn, currently zero repos), and `ws-deepen` (scope-expansion/upsell, currently zero repos). Two of the three long-term drivers under this North Star are unbuilt today.
- Anchorage's equity pilot itself is a long-term payoff structure: "even 1% is $40M" tied directly to sustaining client experience through an AI overhaul, not a one-time deliverable.
- A staged, multi-step roadmap toward a possible client-facing console (anchorage-review-console: local, done, to server-side feedback, to session resume/fork, to in-document review, to possibly client-facing) exists but each later step is explicitly optional/undecided.
- A relationship knowledge-graph with "relationship health" scoring is sketched (mima's Phase 2) as a pattern, but per the mima-exclusion correction this should be treated as a reusable idea to potentially reinvent inside the Agent OS product, not as an inherited feature or roadmap commitment.

## People + relationships

- **Jarred Winn**, Winn Solutions. Principal across every thread in this dossier.
- **Allan Marshall**, CEO of Upexi (a Solana Digital Asset Treasury company), founder of XPO Logistics (grown to roughly a $17B public company), not on social media by choice. Two distinct relationship tracks with Jarred that this dossier confirms are the same person referred to two ways: (a) an active, ongoing Winn.solutions ghostwriting and capital-strategy-advisory client engagement, with a documented approval chain (Jarred drafts, Brian Rudick edits, Allan approves) and a secret voice-guide gist; (b) the target first pilot and investor for the new Agent OS concept, referred to as "Alan" in the 2026-07-08 call notes, pitch $10 to 50M, meeting targeted 7/17-18. Confirmed the same entity via direct read of the primary tracking thread (see Grey areas).
- **Brian Rudick**, the editorial gate in Allan Marshall's content approval chain.
- **Nathan McCauley**, co-founder and CEO of Anchorage Digital. The client whose sole stated constraint on the AI-overhaul equity pilot (2026-06-30) is client experience. Anchorage: $4B valuation, $60B AUM, already paying a $25k/mo retainer.
- **Nick Metzler**, game designer with a tokenomics and behavioral-psychology background and a Framework Ventures history, nick@winwin.game. Co-founder-conversation participant with Carter Razink and Jarred on 2026-07-08. Owes a gamification mechanics definition by 7/31. Not confirmed to be the same "Nick" as a 2026-06-25 CRM entry for "Nick from Recall.ai" (see Grey areas); treat as unconfirmed.
- **Carter Razink**, physics and math background, serial founder, ex-stablecoin-rewards CTO, carter@raz.ink. Co-participant on the same 2026-07-08 call. Owns "Recurro," his own recursive-self-improvement framework for engineering orgs (not the joint product's name). Cited case study: his 4-engineer team at 16x baseline versus an 18-engineer control team at 2.5x. Owes a Recurro doc (7/10), a matrix.build GUI-inspiration link (7/9), and the packaged 16x case study (7/15). Distinct from a different "Carter" (a Spree/travel-tech AI engineering leader) referenced in an unrelated 2026-06-09 automation-program thread; do not conflate the two.
- **Kate Roling, Erin DeMarco, Joe McNaney, Sam Gentile, Jen Hunnewell**: named client-side reviewers on the Anchorage deck feedback loop (`anchorage-agentic-preview/INTENT.md`, 2026-06-22).
- **TM Lee, Bobby Ong**: CoinGecko client contacts (`knowledge/INDEX.md`).
- **Pat Yiu**: co-developer/ally, trust score 9.5/10 and rising per `relationship-map.md` (2026-04-27).
- **Atticus Khrin**: Friction co-founder, trust score 4/10, marked "tested," same source.

## Artifacts (paths, repos, commits, docs, decks)

Repos and key files:

- `/Users/jarredwinn/Projects/fieldy-clawdia/memory-bank/decisions/0006-fieldy-crm-wiring-llm-mapper.md`, `/Users/jarredwinn/Projects/fieldy-clawdia/tooling/fieldy-crm-sync.py`
- `/Users/jarredwinn/Projects/brain/docs/architecture.md`, `docs/related-repos.md`, `docs/belief-system.md`, `README.md`
- `/Users/jarredwinn/Projects/clawdia-atlas/README.md`, `docs/00-overview.md`, `docs/02-agent-architecture.md`, `docs/03-meeting-ingest-pipeline.md`, `docs/04-tooling.md`, `docs/06-processes-and-crons.md`, `docs/09-open-questions-and-conflicts.md`, `diagrams/stack-overview.md`
- `/Users/jarredwinn/Projects/anchorage-agentic-preview/review/REGENERATE.md`, `versions/ingest-feedback.sh`, `INTENT.md`
- `/Users/jarredwinn/Projects/anchorage-review-console/INTENT.md`
- `/Users/jarredwinn/Projects/anchorage-workspace/BACKLOG.md`, `README.md`, `00-orientation/relationship-map.md`, `Nathan McCauley/01_STRATEGY/AI_GTM_2026-06/gdoc-exports/feedback-ledger.md`, `Nathan McCauley/LONGFORM/who-banks-the-agents-v3/build/kate-comments-2026-07-02.json`, `99-source/archive-snapshots/friction-anchorage-original-20260419-151127/media/clients.md` and `pipeline.md`
- `/Users/jarredwinn/Projects/claudecode-bar/main.swift` (`reviewQueueRows()`, lines ~2360-2400, commit 866068a), `docs/recall-docs-panel-plan.md`
- `/Users/jarredwinn/Projects/executive-agent-gui/research/vision-brief.md`, `research/raw/collation-2026-07-03.md`, `memory-bank/2026-07-03-birth-thread.md`
- `/Users/jarredwinn/Projects/knowledge/INDEX.md`, `AGENTS.md`, `3-resources/people/allan-marshall.md`, `REPO-PORTFOLIO.md`
- `/Users/jarredwinn/Projects/the-sage/goals/goals.json` (objective id "ws")
- `/Users/jarredwinn/Projects/command-center/CLAUDE.md` (negative finding)
- `/Users/jarredwinn/Projects/teamclaude-fleet/INTENT.md` (negative finding)
- `~/Projects/anchorage-review-console` (repo root, referenced but not opened by any reader; flagged as a lead)

Decks and documents:

- `/private/tmp/mima_story_v3.pdf` (Feb 2026 concept, exported 2026-07-07); mima_story_v2.docx referenced but not located
- `/Users/jarredwinn/Projects/miscellaneous/allan-ai-deck/deck.html` (v12, 2026-07-07)

This-worktree and miscellaneous project artifacts:

- `/Users/jarredwinn/.omnara/worktrees/miscellaneous/knelt-smugness/threads/2026-07-08-agent-os-product-concept-consolidation.md` (primary tracking thread for this whole swarm, read directly)
- `/Users/jarredwinn/.omnara/worktrees/miscellaneous/knelt-smugness/research/inbox/product-sweep-2026-07-08/swarm-gui.md` and `swarm-allan-marshall.md` (sibling dossiers, cross-checked directly to resolve the Alan/Allan Marshall identity question)
- `/Users/jarredwinn/Projects/miscellaneous/DEBRIEF.md` (negative finding)
- `/Users/jarredwinn/Projects/miscellaneous/threads/2026-07-01-yesterdays-conversations-review.md`, `2026-06-17-clickup-ops-and-action-item-system.md`, `2026-06-18-macro-lesson-audit.raw.json`, `2026-06-20-version-history-dashboard.md`, `2026-07-07-winn-ai-bot-meet-anchorage.md`, `2026-06-11-arthur-av-repo.md`
- `/Users/jarredwinn/Projects/miscellaneous/memory-bank/lessons.md` (2026-06-25 and 2026-06-21 entries)
- `/Users/jarredwinn/Projects/miscellaneous/org/objective-ledger.yaml`, `org/README.md`
- `/Users/jarredwinn/Projects/miscellaneous/threads/_filed/executive-agent-gui/README.md`

mini (`clawd@mini`) scripts and paths:

- `~/.openclaw/workspace/scripts/crm-followup-prep.py`, `crm-automation.py`, `crm-decay-alert.py`, `crm-decay-scorer.py`, `crm-staleness-watch.py`, `crm-cache.py`, `mempalace-crm-unify.py`, `hubspot-crm.py`, `hubspot-sync-contacts.py`
- `~/.openclaw/workspace/scripts/meeting-review/app.html` ("Clawdia, Meeting Intelligence" internal dashboard)

External references (named but not opened by any reader; carried forward as leads, not verified facts):

- `~/.claude/skills/client-feedback/registries/anchorage.json`
- `github.com/Winnsolutionsadmin/anchorage-deck-feedback` (GitHub issues as the feedback-queue backing store)
- `github.com/Winnsolutionsadmin/skills-registry/_meta/program-log.md` (used to disambiguate the two "Carters")
- Notion "Network CRM DB" and Obsidian `crm/{contacts,pipeline,follow-ups,interactions}`, described as the live personal CRM backing the clients.md/pipeline.md snapshots, not located inside any reader's corpus.

## Timeline of key moments

- **2026-03-17/18**: Personal CRM `clients.md` and `pipeline.md` created (relationship-decay formula, sales-pipeline schema).
- **Feb 2026**: mima concept authored (client management listed as a liaison function; later excluded from Agent OS, see 2026-07-08 below).
- **2026-04-16**: CRM write-ownership transferred from the "Executive" agent to main/Clawdia, in an agent cull.
- **2026-04-19**: friction-anchorage-original snapshot archived (containing the 3/17-18 clients.md/pipeline.md).
- **2026-04-27**: `relationship-map.md` snapshot taken (trust scores, introduction graph).
- **2026-05-26**: anchorage-workspace repo imported; BACKLOG.md records Jarred's vision for sub-branches per client.
- **2026-06-01**: fieldy-crm-sync.py decision (0006) formalized; Fieldy meetings begin writing directly into the canonical CRM.
- **2026-06-15**: clawdia-atlas docs verified as current: CRM, Lobster pre-meeting briefing pipeline, and MemPalace crm wing all documented as live.
- **2026-06-16**: brain repo created; 10-step meeting-ingest pipeline documented, with CRM contact resolution as step 1 and the "Clarify" rung flagged as not built.
- **2026-06-17**: ClickUp per-client action-item tracker design thread (client items routed through Jarred, unlike direct employee pings).
- **2026-06-18**: Macro lessons formalized on quote-provenance verification for client-facing deliverables and client-onboarding-intake constraints; `/newclient` skill audited.
- **2026-06-20**: version-history-dashboard thread documents the org-to-client-to-project-to-document Drive hierarchy and an internal dashboard mockup.
- **2026-06-21**: Anchorage deck confirmed under active editing in a browser session, the earliest directly confirmed editing-session date found for that deck.
- **2026-06-22**: anchorage-review-console INTENT.md authored (staged client-facing roadmap); anchorage-agentic-preview INTENT.md authored (named client reviewers, Google Docs/spreadsheet feedback decision); `the-sage/goals.json` "ws" objective updated (Deliver & retain Winn.solutions clients North Star; ws-retain and ws-deepen left at zero repos).
- **2026-06-23**: anchorage-agentic-preview review/REGENERATE.md documents the GitHub-issues feedback loop.
- **2026-06-25**: A mini CRM entry logs "Nick from Recall.ai" giving a live SDK demo (possibly a different Nick than the 7/8 call; unresolved). Separately, a macro lesson is drawn from a CDSS document-prep incident (confirm format and channel up front for client deliverables).
- **2026-06-26**: claudecode-bar `/rq` review-queue feature committed (866068a); `recall-docs-panel-plan.md` records an open question on modeling "client" as a grouping concept.
- **2026-06-28**: `REPO-PORTFOLIO.md` flags Anchorage's client-facing/review tooling (deck, sprint-ssot, agentic-preview, review-console) for consolidation into one workspace.
- **2026-06-30**: Nick Metzler call with Jarred; Anchorage's "client experience" sole constraint surfaces; a client complains about an uninvited notetaker bot ("F***ing Winn AI keeps following me").
- **2026-07-01**: `yesterdays-conversations-review.md` digests the 6/30 call; CRM data-quality bugs flagged (mis-transcription, double-ingestion); a daily Slack client checklist ritual is noted as the team's first priority; an engagement/churn watchdog concept is proposed (#4 of 8 ranked ideas that day).
- **2026-07-02**: `org/objective-ledger.yaml` and `org/README.md` snapshots record anchorage-review-console, client-style-guides, and kindred-portal entries; client_work tagged as 18 of 126 tracked repos, described as real revenue.
- **2026-07-03**: executive-agent-gui's vision-brief and birth-thread written; the "executive briefing surface" is framed as a candidate client-experience layer and face of the enterprise pitch; "the Nick track" is already referenced this early, five days before the recorded call.
- **2026-07-05**: `knowledge/INDEX.md` snapshot records the per-client scaffold populated for Anchorage, Upexi, CoinGecko, Shinzo, 0G, Internal, Winn.Solutions, and 67 archived former clients.
- **2026-07-07**: The "Winn.ai" notetaker bot is confirmed joining a live Anchorage Digital weekly sync; Jarred orders a full remediation purge (Google OAuth revoked on 16 apps, 7 Zoom Marketplace apps removed, Zoom AI auto-start disabled). Separately, allan-ai-deck v12 is finalized with its mima-pattern demo slide, and the mima_story_v3 PDF is exported.
- **2026-07-08**: Nick Metzler, Carter Razink, and Jarred hold a three-way call (roughly 11:05am to 12:15pm PT, 68 minutes), captured redundantly three times by Fieldy and Recall pipelines. Jarred issues authoritative corrections (mima excluded from Agent OS; Recurro is Carter's own concept; the joint product is currently unnamed). This synthesis swarm runs the same day.

## Sources (cite transcript/file paths + dates)

- `executive-agent-gui/research/raw/collation-2026-07-03.md`, line 178, quoting the 2026-06-30 Nick Metzler call, digested 2026-07-01, collated 2026-07-03.
- `executive-agent-gui/research/vision-brief.md`, lines 96-100, compiled 2026-07-03.
- `/private/tmp/mima_story_v3.pdf`, pp. 1-9 (problem statement ~line 64, client management ~line 111, interaction loop ~line 191-193, target personas ~line 270-271, Phase 2 roadmap ~line 340-345, competitive landscape ~line 376-377), source concept Feb 2026, PDF generated 2026-07-07.
- `miscellaneous/allan-ai-deck/deck.html`, lines 556-558, v12, current as of 2026-07-07.
- `claudecode-bar/main.swift`, `reviewQueueRows()` ~lines 2360-2400, commit 866068a, 2026-06-26.
- `claudecode-bar/docs/recall-docs-panel-plan.md`, "Open question for next session" section, 2026-06-26.
- `fieldy-clawdia/memory-bank/decisions/0006-fieldy-crm-wiring-llm-mapper.md`, 2026-06-01.
- `fieldy-clawdia/tooling/fieldy-crm-sync.py`, deployed to mini, cron 600s, undated.
- `anchorage-agentic-preview/review/REGENERATE.md`, 2026-06-23.
- `anchorage-agentic-preview/versions/ingest-feedback.sh`, undated.
- `anchorage-workspace/BACKLOG.md`, repo imported 2026-05-26.
- `anchorage-review-console/INTENT.md`, authored 2026-06-22, repo present since 2026-06-18.
- `anchorage-agentic-preview/INTENT.md`, authored 2026-06-22.
- `anchorage-workspace/Nathan McCauley/01_STRATEGY/AI_GTM_2026-06/gdoc-exports/feedback-ledger.md` and `feedback-audit-2026-07-07.md`, 2026-07-07.
- `anchorage-workspace/00-orientation/relationship-map.md`, snapshot 2026-04-27.
- `anchorage-workspace/99-source/archive-snapshots/friction-anchorage-original-20260419-151127/media/clients.md` and `pipeline.md`, created 2026-03-17/18, archived 2026-04-19.
- `/Users/jarredwinn/.omnara/worktrees/miscellaneous/knelt-smugness/threads/2026-07-08-agent-os-product-concept-consolidation.md`, read directly in this pass, 2026-07-08 (call content, corrections, GTM, moat quote, Alan/Allan Marshall identity).
- `executive-agent-gui/memory-bank/2026-07-03-birth-thread.md`, 2026-07-03.
- `miscellaneous/memory-bank/lessons.md`, entries dated 2026-06-25 and 2026-06-21.
- `command-center/CLAUDE.md`, last commit 2026-06-17 (negative finding).
- `teamclaude-fleet/INTENT.md`, repo last touched ~2026-06-22 (negative finding).
- `brain/docs/architecture.md`, `docs/related-repos.md`, `docs/belief-system.md`, repo created 2026-06-16.
- `knowledge/INDEX.md`, snapshot 2026-07-05.
- `knowledge/AGENTS.md`, snapshot 2026-07-05.
- `knowledge/3-resources/people/allan-marshall.md`, last reviewed 2026-06-02.
- `miscellaneous/org/objective-ledger.yaml`, snapshot 2026-07-02.
- `knowledge/REPO-PORTFOLIO.md`, dated 2026-06-28.
- `miscellaneous/org/README.md`, snapshot 2026-07-02.
- `the-sage/goals/goals.json`, objective id "ws," updated 2026-06-22.
- `miscellaneous/threads/2026-07-01-yesterdays-conversations-review.md`, logged 2026-07-01, describing 2026-06-30 conversation.
- `~/Projects/anchorage-review-console` (repo, not opened directly by any reader).
- `github.com/Winnsolutionsadmin/skills-registry/_meta/program-log.md`, log entry 2026-06-09, graduated 2026-06-12, referencing a 2026-06-05 meeting.
- mini `~/.openclaw/workspace/scripts/crm-followup-prep.py`, `crm-automation.py`, `mempalace-crm-unify.py`, `hubspot-crm.py`, `crm-decay-alert.py`, `crm-decay-scorer.py`, `crm-staleness-watch.py`, `crm-cache.py`, undated, currently present.
- mini `~/.openclaw/workspace/scripts/meeting-review/app.html`, undated.
- `miscellaneous/DEBRIEF.md`, 2026-07-03 (negative finding).
- `clawdia-atlas/README.md`, `docs/00-overview.md`, `docs/02-agent-architecture.md`, `docs/03-meeting-ingest-pipeline.md`, `docs/04-tooling.md`, `docs/06-processes-and-crons.md`, `docs/09-open-questions-and-conflicts.md`, `diagrams/stack-overview.md`, all verified 2026-06-15.
- `research/inbox/product-sweep-2026-07-08/swarm-gui.md` and `swarm-allan-marshall.md`, read directly in this pass (2026-07-08) to resolve the Alan/Allan Marshall identity question.

## Confidence notes (what is solid vs thin)

Solid, well-evidenced, corroborated across independent reader passes:

- The CRM and meeting-capture technical stack (fieldy-crm-sync, the brain pipeline, clawdia-atlas's documented functions, the mini script stack) is real, running infrastructure, not a proposal. Multiple independent readers found the same pieces from different corpora with direct doc quotes.
- Anchorage's "client experience" constraint and the equity-pilot numbers are quoted directly and cross-referenced by at least three separate reader passes.
- The 2026-07-08 call content and Jarred's corrections are solid: read directly from the primary tracking thread in this pass, not secondhand through a reader summary.
- Allan Marshall equals "Alan" is now solid, resolved by direct primary-source read in this pass, correcting a grey area that two sibling dossiers had each independently flagged as unconfirmed based on their narrower corpora.
- The absence of a unified client CRM or client-facing portal product is solid: six independent reader passes across roughly a dozen distinct corpora all returned this same negative finding, with no single contradicting hit anywhere.

Thin, unconfirmed, or explicitly speculative:

- Whether "Nick Metzler" and "Nick from Recall.ai" are the same person: no reader found a direct cross-reference either way. Treat as an open question, not a fact, in either direction.
- Whether any internal review console (anchorage-review-console or its successors) will ever ship client-facing: explicitly staged and optional in the source docs, not committed anywhere.
- mima's relationship-health/knowledge-graph feature as applicable prior art for the Agent OS product: technically well documented, but formally out of scope per Jarred's 2026-07-08 correction, so its relevance here is pattern-level inspiration at most, not an inherited roadmap item. Any downstream overview should not list it as an Agent OS feature.
- The literal "client portal" concept named in the goal context (as something Jarred may have discussed, e.g. with Allan Marshall or in the GUI concept) was not found as an artifact anywhere. If it exists, it exists only in conversation not yet captured in any file this swarm reached, most likely in the raw 2026-07-08 meeting transcripts (mini `~/.openclaw/workspace/fieldy/transcripts/2026-07-08.jsonl`) or in corpora assigned to other topic readers (GUI, gamification, Allan Marshall, anchorage) rather than this one.
- Several leads were not run to ground in this pass, per the "do not re-run the full search" instruction: the `~/.claude/skills/client-feedback/` registries beyond the one quoted excerpt, the `anchorage-deck-feedback` GitHub issue history, the raw 2026-07-08 transcripts, and Notion/Obsidian CRM stores referenced but never opened by any reader. These remain gaps, not resolved absences.
