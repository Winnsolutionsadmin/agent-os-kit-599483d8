# Meeting Capture Stack: Fieldy, Recall.ai, Notetakers, Speaker Attribution, Nick and Carter

Synthesis of 6 independent reader passes plus direct re-reading of 3 primary sources
(`threads/2026-07-08-agent-os-product-concept-consolidation.md`, `executive-agent-gui/research/vision-brief.md`,
`miscellaneous/threads/2026-07-06-recall-notetaker-not-working.md`). Compiled 2026-07-08.

## Headline

"Fieldy and Recall" are not a company Nick and Carter work for. They are Jarred's own meeting-capture
infrastructure: Fieldy is his ambient wearable-capture pipeline, and Recall is Recall.ai, a third-party
meeting-bot SDK he integrated into his own "recall-notetaker" app. Fieldy and Recall are the tools that
recorded today's (2026-07-08) call, not the affiliation of the people on it. The primary source for
today's call states this directly: "pull today's Nick/Carter call from Fieldy + Recall" (i.e., pull it
using those two capture tools). Nick Metzler and Carter Razink are independent collaborators on a
separate, currently-unnamed gamified "Agent OS" concept, introduced to Jarred as a 3-way group for the
first time on 2026-07-08. No document in any of the 6 corpora searched, across roughly a dozen repos and
threads, shows a company called "Fieldy" or "Recall" that Nick or Carter represent. This should be
treated as resolved pending Jarred's explicit confirmation, per this task's own instruction to verify
naming rather than assume it.

A second, equally load-bearing correction, made by Jarred himself in the same primary thread and marked
authoritative: the working name "Recurro" is Carter's own separate framework (his term for recursive
self-improvement applied to engineering orgs), not the joint product's name. The joint Agent OS / RSI-for-orgs
product is currently unnamed. Earlier framing (including this task's own goal context) calling Recurro a
"working name candidate" for the joint product is superseded by this correction and should not be repeated
downstream without the caveat.

## Scope note

This dossier covers the meeting-capture technical stack (Fieldy, Recall.ai, ingest pipelines, speaker
attribution) and the identity/relationship questions around Nick and Carter, because those were the
explicit assignment. It does not attempt to cover the Agent OS / gamification product concept itself,
the Allan Marshall deck's full content, or mima; those are separate tracks in the same swarm
(`swarm-gui.md`, `swarm-mima.md`, `swarm-allan-marshall.md` in this same directory) and are mentioned
here only where they intersect with capture infrastructure or identity questions.

## What exists / was built

Two distinct capture efforts exist under the "meeting capture" umbrella, built in what looks like two
separate tracks that converge on the same downstream stores but are documented in different repos:

**(A) The ambient multi-vendor pipeline** (owned in `fieldy-clawdia`, `brain`, `clawdia-atlas`; oldest,
most mature, dates to at least May 2026):
- Otter.ai: cloud transcription, deliberately kept as a permanent redundant layer since a 2026-05-13
  decision, specifically because it uses a different vendor/STT/failure-mode than Fieldy.
- Fieldy: a wearable ambient-capture device with its own cloud API. Hybrid ingestion: webhook real-time
  + v2/v3 API backfill + MCP query. Can legitimately be offline up to 7 days without that being a fault
  (a monitoring bug in 2026-06-22 false-flagged it as stalled before this was corrected).
- Granola.ai (poll-based, ADR-0011) and Roam/Ro.am (real-time HMAC webhook via Tailscale Funnel,
  ADR-0014): both added by 2026-06-17, both verified with synthetic data only as of that date, no
  confirmed real-meeting acceptance test found in any corpus.
- Omi, Plaud, Screenpipe named as sources/comparables in `brain/docs/architecture.md`. Screenpipe is
  scaffolded (empty dir on mini) but not in active use, per this task's own goal context.
- Pipeline flow (per `clawdia-atlas/docs/03-meeting-ingest-pipeline.md`): source app to Zapier to n8n
  (Hetzner :5678) to gateway (mini :18789) to a Clawdia agent to `run-pipeline.py`, producing a meeting
  note, a CRM update, a Notion entry, a memory entry, and a Signal digest, then embedded via gbrain-sync.
- Storage as assessed 2026-06-04: 343 processed meeting notes (YAML frontmatter + wikilinks), 298
  structured JSON records, a 47,397-embedding semantic index (gbrain/Chroma). Verdict at the time: "~85%
  built and adequate. Do NOT rebuild. Add the missing 15% (discoverability + dashboards)."
- Downstream automation: `fieldy_to_clickup.py` armed in shadow mode as of 2026-07-01 (live proof: 5 real
  tasks extracted from one meeting); Notion Meeting Notes DB and Action Items DB under the Command Center
  page.

**(B) The Recall.ai meeting-bot integration** (owned in `claudecode-bar`, plus a mini-side bridge; newer,
first evidence around 2026-06-25 to 2026-06-28):
- `recall-notetaker`: an Electron app that auto-detects and records Zoom/Meet/Teams meetings via the
  Recall.ai SDK/API, writes `~/.claude/recall-status.json` on every state change plus a 30-second
  heartbeat, and links out to the real Recall.ai account dashboard
  (`https://us-west-2.recall.ai/dashboard`).
- `hud.html`'s Recall tile (in claudecode-bar, the menu-bar HUD) reads that status file and renders a
  live transcript panel with per-speaker labels (an `rc-spk` span) and partial/interim results, in a
  40-line rolling auto-scroll window (a live-scroll bug was fixed 2026-07-07, commit `cf3fc9e`).
- Shipped 2026-06-28: switched from a rejected realtime provider to async transcription
  (`recallai_async`) specifically to get real speaker names into gbrain, then added native low-latency
  realtime streaming (English-only, `recallai_streaming`) plus a `desktop_sdk_callback` for the live bar
  transcript.
- `recall-bridge.py` on mini: a self-contained bridge with three bearer-authed endpoints (`/gate`
  calendar-gate and upload-token mint, `/land` deterministic landing, `/complete` polls Recall until
  transcript ready then lands), deliberately isolated from the core gateway config so it is removable.
- Record-on-detection is a deliberate design decision by Jarred (2026-06-25, reaffirmed 2026-07-01):
  every SDK-detected meeting is recorded regardless of calendar invite. The resulting client-visible
  "notetaker joined" announcement is an accepted cost, explicitly not to be re-litigated.
- Security hardening: live meeting-transcript text is treated as untrusted/externally-influenced content
  and base64-encoded before crossing the JS bridge, closing a string-breakout injection path from meeting
  audio content into the app.
- As of the last update to `brain/docs/architecture.md` (2026-06-16), `fieldy-clawdia` (last commit
  2026-06-19), and `clawdia-atlas` (last commit 2026-06-19), Recall.ai has zero mentions in any of the
  three. Confirmed independently by four different readers via direct grep of each repo. This means
  track (B) was built without being folded into the "official" documented architecture that governs
  track (A), at least as of those dates.

**Convergence and redundancy**: both tracks feed the same downstream stores (gbrain, CRM). This has
caused at least one confirmed double-ingestion: a Nick Metzler call on 2026-06-30 was recorded by both
Otter and Recall with different dedup keys, producing two separate CRM entries for one call. Today's
2026-07-08 Nick/Carter call was itself captured three times (once fieldy-extracted, twice via Recall,
at three different timestamps between 11:25 and 12:21) plus a 149KB raw JSONL transcript, which the
primary thread for that call treats as one source event to be cross-read, not triple-counted.

**Other built pieces relevant to this stack**: a probabilistic speaker-presence model and per-utterance
turn attribution (see Speaker attribution below); a reliability/ops layer (BrainStatus skill, ReplayMeeting
skill with 4 recovery input modes, `fragility/heartbeats.json` monitoring, added for recall-notetaker
specifically on 2026-07-06); and a client-facing competitor-eviction effort that removed unwanted
third-party notetaker bots (Read AI, custom-named "Winn.ai", and Fireflies.ai) from Anchorage's Zoom
Marketplace and Google Calendar auto-join, confirmed resolved in this repo's own git history (commits
`9376e121` and `881dcde8`, both 2026-07-07).

## Key features

- Auto meeting-detection and bot-join for Zoom/Meet/Teams with no calendar invite required
  (record-on-detection, a deliberate design choice, not a bug).
- Live in-app transcript panel with per-speaker labels and partial/interim (not-yet-final) results,
  auto-scrolling.
- Async post-call transcription specifically to recover real speaker names (Recall.ai async mode).
- Always-on ambient wearable capture (Fieldy) with 3-tier auto-classification: business meetings get the
  full pipeline (CRM, notes, memory, retrievable transcript), topical chatter goes to memory only,
  personal conversations are quarantined off the gbrain-indexed path (142 notes moved in one backfill).
- Cross-vendor redundancy by design (Otter kept permanently alongside Fieldy on purpose, since 2026-05-13)
  paired with cross-vendor dedup by conversation ID or dedup key, though dedup has repeatedly failed in
  practice (the 2026-06-30 double-CRM-entry incident; today's 3x capture of one call).
- A meeting-level probabilistic speaker "presence" model: owner prior + self-introduction/vocative regex
  + CRM co-occurrence + calendar-attendee match, combined with a weighted noisy-OR, and an explicit design
  principle of flagging ambiguous speakers rather than guessing.
- Per-utterance turn attribution layered on top of the presence model plus time-gap turn segmentation
  (not acoustic diarization), which works well for 2-person calls and degrades hard on 3+ person calls.
- Downstream automation: CRM sync, Notion Meeting Notes and Action Items databases, ClickUp task
  extraction (shadow mode), a Signal digest, and gbrain semantic embedding for later recall.
- Retrieval skills: `fieldy-find`, `fieldy-recent`, `fieldy-digest` (mini-only), `BrainStatus` (layer-by-layer
  pipeline diagnosis), `ReplayMeeting` (recovery from n8n execution ID, Otter .txt export, a pre-formed
  payload, or a pasted transcript).
- Security: meeting-transcript text is handled as externally-influenced/untrusted input (base64-encoded
  across the JS bridge), not as trusted local data.
- Active curation of which third-party notetaker bots are allowed into client meetings (Anchorage), as
  opposed to passively accepting whatever auto-joins.
- A `/recall` Claude Code skill exists in this very environment's skill list, and per one reader it
  queries the gbrain corpus (hot-memory MCP tool: `recall`, `extract_facts`, `forget_fact`), not raw
  meeting transcripts. This is a third, separate thing also named "recall," confirmed directly by this
  agent's own tool list, not just a reader's grep.

## Must-haves

- Capture every real business meeting; never silently drop one; filter out non-business chatter; classify
  correctly. This became an explicit directive from Jarred after a 2026-05-22 incident where business
  meetings were silently dropped while family chatter was captured and stored as "meetings."
- A concrete latency bar: within a minute of a conversation ending, the data should be ingested, in
  memory, and fully retrievable as a transcript (founding goal, 2026-05-21), later refined into a
  committed SLO of 30 to 60 seconds from ASR-ready to retrievable, against a measured Fieldy ASR
  median of 8.4 minutes (p90 27.5 min, p99 41.8 min, n=47 over 7 days).
- Speaker attribution must flag ambiguity rather than guess or fabricate an identity. This is stated as
  an explicit design principle (decision 0012), reacting against a rejected v1 that repeatedly asked
  Slack "is this Jarred? (40%)".
- Every capture path needs active failure monitoring; silent failure is the recurring root cause of data
  loss across this stack (see Reliability track record in the timeline). The stated lesson from the
  2026-07-06 recall-notetaker outage: "silence must look like breakage," i.e., disabled/dead components
  must fail a heartbeat check, not just stop quietly.
- Untrusted content discipline: transcript text captured from live meeting audio must be treated as
  externally-influenced input and isolated from code execution paths (the base64 bridge hardening).
- Client-facing bot hygiene: unwanted or unbranded third-party notetaker bots must not be allowed into
  client meetings; this was enforced concretely by evicting Read AI and Fireflies.ai from Anchorage's
  Zoom Marketplace and Google Calendar auto-join in 2026-07-06/07.
- "Make meetings pay off": automatically extracting decisions, action items, and attendees from captured
  meetings into ClickUp/gbrain is explicitly named (2026-06-28) as the biggest deferred ROI lever of the
  whole stack. As of that date it was described as not built, but it is treated as a requirement, not an
  optional nice-to-have, and per the Allan Marshall deck (see Value propositions) it is now the headline
  external value proposition too.
- Dedup across redundant capture pipelines remains an unmet requirement in practice, evidenced most
  recently by today's (2026-07-08) call being captured three separate times.

## Grey areas and open questions

- **Speaker-attribution vendor decision is open.** A ClickUp board task, "Decide between Jamie AI and
  Recall.ai speaker attribution path," was still open as of 2026-07-06 per the thread that resolved an
  unrelated recall-notetaker outage that same day. No owner, due date, or decision criteria were found
  in any corpus. "Jamie AI" itself returned zero content hits anywhere searched, so there is no
  documented comparison of it against Recall.ai to draw on.
- **The presence model and turn-attribution work are validated but not deployed.** Both decision 0012
  (meeting-level presence model, 2026-06-16) and decision 0013 (per-utterance turn attribution,
  2026-06-17) show real validation results (for example, one call went from "Jarred ~0.40 unknown" to
  "Sinan@0.95, Jarred@0.90" under the new model) but explicitly say "NOT deployed. Worktree branch only,"
  with no launchd job. Whether this has since shipped is unknown from this pass.
- **The speaker-attribution funnel is half-built.** Per `brain/docs/architecture.md` (2026-06-16), the
  funnel is Identify (built) to Verify (partial, a Tier-2 LLM verify stage is stubbed and deferred per
  ADR-0009, blocked on an API key) to Clarify (not built, called "the missing rung") to Publish (built).
  A registered launchd job, `fieldy-speaker-reconcile`, could not be matched to any script in the
  workspace tree as of the last check in that repo, a possible broken reference that was not resolved.
- **Granola and Roam ingestion are unproven on real meetings.** Both were verified only against synthetic
  data as of 2026-06-17; no real acceptance test was found in any corpus.
- **Identity: is "Nick from Recall.ai" the same person as Nick Metzler?** One reader found that mini's
  `crm/interactions/nick.md` merges a 2026-06-25 entry (Nick, of Recall.ai, gave a live desktop-SDK demo)
  with 2026-07-08 entries about Nick Metzler (game designer, `nick@winwin.game`). The reader's read is
  that these are two different people conflated by first-name-only contact matching, since no other
  evidence anywhere ties Nick Metzler to Recall.ai. This was not independently re-verified in this pass
  (no mini access was exercised for this specific file) and should be confirmed directly with Jarred
  before being stated as fact either way.
- **Identity: is the unconfirmed "Carter" in executive-agent-gui's vision brief the same as Carter
  Razink?** Directly re-read for this dossier: `executive-agent-gui/research/vision-brief.md` (compiled
  2026-07-03) flags "Carter" as "unconfirmed across all local records, possibly a mis-tagged attendee,"
  with "no verified real executive attached to this product." The same document separately describes a
  "Nick track" (AI Work Terminal / enterprise adoption, gamified scoring) as adjacent to the exec-GUI
  concept, and notes a "second Nick meeting" on 2026-07-03. Given that today's (2026-07-08) call
  introduces Carter Razink alongside Nick Metzler for gamified Agent-OS work, it is plausible the
  2026-07-03 "Carter" reference is an early, unconfirmed mention of Carter Razink. This is a plausible
  connection, not a proven one; the vision-brief text itself explicitly declines to confirm it, and no
  later document was found that closes the loop.
- **A different "Carter" did not appear on an earlier tape.** On the 2026-06-19 Fieldy-recorded call that
  seeded the original "life-OS" product vision, a named attendee "Carter" was expected but does not
  appear on tape (attendees resolved as Jarred plus "unknown-1"). This was flagged to Jarred and, per
  `activeContext.md`, was still an open loop as of the last write found. Whether this expected-but-absent
  Carter is Carter Razink is unknown.
- **"Carter" is a heavily overloaded name across this estate, independent of the above.** Confirmed
  distinct, unrelated usages: "Carter (Spree)" as a CRM alias for an unrelated contact; an internal
  "Carter automation-stack integration" program (skills-registry PRs, graduated 2026-06-12); a Carter
  test-fixture name inside the fieldy-clickup eval harness; and a git worktree once named
  "analyze-carter-automation-integration" that no longer appears in `git worktree list`. None of these
  should be assumed to be Carter Razink.
- **"Recall" is a three-way naming collision inside this estate**, independent of the Recall.ai question:
  (1) the meeting-bot integration covered in this dossier; (2) an entirely unrelated local
  session/file smart-search panel in claudecode-bar (`recall-backend` binary plus `recall.html`, an
  Fn-key-triggered panel that searches Claude session transcripts and edited files, graduated 2026-06-26);
  (3) a Claude Code `/recall` skill that queries the gbrain corpus. Downstream readers should not conflate
  any of these.
- **Whether Nick and Carter have any connection to a company literally named Fieldy or Recall** was
  searched for across all 6 reader passes (roughly a dozen repos and the full miscellaneous threads
  directory) and found nowhere. This should be treated as effectively answered (no), pending Jarred's own
  confirmation, rather than left open indefinitely, since the goal context's framing asked specifically
  for this to be verified rather than assumed.
- **Whether Recurro survives in any form for the joint product** is closed by Jarred's own correction
  (see Headline): Recurro is Carter's separate framework name, and the joint product is unnamed. Flagging
  here only because multiple upstream materials, including this task's own goal context, still describe
  Recurro as a floated working name for the joint concept; that framing is now superseded.
- **No competitive comparison exists** of Recall.ai against Jamie AI, Fathom, Fireflies, or Read AI for
  the specific purpose of speaker attribution or meeting capture generally. This is a real gap, flagged
  here for the downstream competitive/risk-analysis track (3.2), not something this pass could resolve.
- **Today's gbrain embedding status is reported stale** (per this task's own goal context: OpenAI
  embedding quota exhausted since 00:16 UTC today, both scheduled sync runs failing 10 of 10 files,
  today's three meeting notes near-certainly unembedded as of writing). This was not independently
  re-verified in this pass and is passed through as reported, not confirmed firsthand.
- **7 historical meeting files remain permanently missing** from a 2026-07-02 estate-wide sweep following
  a quota-outage data-loss incident (275 files dropped in total across all historical outages, 7 still
  missing), including some tied to Anchorage deal context. No later document was found reporting these
  as recovered.

## Value propositions

- **Internal/operational**: near-zero-effort meeting-to-system-of-record pipeline. Per
  `clawdia-atlas/docs/03-meeting-ingest-pipeline.md`, "a meeting gets recorded somewhere, and without
  Jarred lifting a finger it becomes a CRM update, a Notion task list, an Obsidian note, a memory entry,
  a Signal digest."
- **Client-facing (clearest external articulation found, from the Allan Marshall deck)**: "Meetings
  should be creative. Agents do the rest." The pitch is that meetings become notetaking-free and
  recap-free, with decisions built in real time while the meeting is still happening. Quoted directly:
  "Nobody takes notes. Nobody recaps. The meeting is creative minds only, and everything it decides gets
  built while you are still in the room." The deck's talk track adds: "The recap email is dead."
- **Quantified ROI claim (same deck)**: before/after timeline collapsing a human chain of meeting to
  notes to review to research to design to execute to report, stated as taking 3 to 4 weeks, down to a
  same-day cycle: the same one-hour meeting, then a 20-minute "thoughts?" check after an agent cluster
  produces notes/actions/research/draft, then a 15-minute decide after a second agent cluster executes,
  chases, and reports. Framed as "Same meeting, 2x the output."
- **Trust and brand-experience angle**: actively curating which bots are allowed into client meetings
  (the Read AI and Fireflies.ai eviction from Anchorage) is itself a value proposition of control:
  meeting capture as a single, sanctioned system rather than an uncontrolled proliferation of competing
  notetaker bots showing up in client calls.
- **Redundancy as reliability, not just waste**: the deliberate decision to keep Otter running forever
  alongside Fieldy specifically because it has different failure modes is a value proposition in itself,
  namely that no single vendor outage should be able to lose a meeting. In practice this redundancy has
  also caused double-ingestion bugs, so the net value depends on dedup logic that is not yet reliable.
- Note: the Agent OS / gamification concept discussed on 2026-07-08 has its own separate value
  propositions (compressing idea-to-execution, gamifying AI adoption, org OKRs tied to agent subtasks).
  Per the scope note above, this dossier does not synthesize those; they belong to other tracks in this
  swarm.

## Goals

### Short-term
- Resolve the open "Jamie AI vs. Recall.ai" speaker-attribution board decision (open as of 2026-07-06,
  no further detail found).
- Decide a production deploy/run-mode for the validated speaker-presence model (a decision explicitly
  left pending as of 2026-06-17).
- Build the "Clarify" stage of the speaker-attribution funnel, the still-missing step that would close
  the loop with the user on ambiguous speaker identities.
- Add "discoverability and dashboards" to the transcript/retrieval system, named as the missing 15% of
  an otherwise "~85% built and adequate" system (2026-06-04 assessment).
- Get a real acceptance test on Granola and Roam ingestion against actual meetings, not just synthetic
  data.
- Fix the recurring pattern of silent capture-path failures before the next one causes data loss (see
  Reliability track record in the timeline); the heartbeat monitoring added for recall-notetaker on
  2026-07-06 is a partial step, not a comprehensive fix across all capture paths.
- Resolve dedup so the same call stops landing as multiple separate meeting notes/CRM entries, directly
  evidenced by today's 3x capture of the Nick/Carter call.

### Long-term
- "Make meetings pay off": full automatic extraction of decisions, action items, and attendees from
  every captured meeting into ClickUp and gbrain, named as the single biggest deferred ROI lever of the
  whole stack (2026-06-28) and, per the Allan Marshall deck, now also the headline client-facing pitch.
- A single, reliable, deduplicated, speaker-attributed transcript-to-memory pipeline that other product
  lines can be built on top of. The evidence across all corpora treats meeting capture as foundational
  infrastructure, not a product in itself. It already underlies the CRM, the Allan Marshall client deck's
  demo, and the capture of the 2026-07-08 Agent-OS ideation call; any future product surface (the
  executive-agent-gui, the Agent OS concept) is likely to depend on this same pipeline rather than build
  its own.
- Resolve the standing architectural split between the two capture tracks (the documented Otter/Fieldy/
  Granola/Roam architecture versus the separately-built Recall.ai integration) so there is one coherent,
  documented picture rather than two.

## People and relationships

- **Jarred Winn**: builds and owns the entire capture stack personally (both tracks), and is the sole
  decision-maker on fixes, vendor choices, and deploy decisions referenced throughout.
- **Nick Metzler**: game designer, tokenomics and behavioral-psychology background, `nick@winwin.game`,
  Framework Ventures background per the 2026-07-08 call notes. A recurring collaborator on the
  gamification/Agent-OS concept since at least 2026-06-30 (a call double-recorded by Otter and Recall,
  where Nick contributed concrete mechanics: leagues with minimum token thresholds, anti-abuse daily
  attainment caps, fake-outlier detection, role-adjusted scoring). A follow-up was locked for 2026-07-03,
  2pm ET (the same day executive-agent-gui was scaffolded), and the first confirmed 3-way call with
  Carter happened 2026-07-08. Not confirmed to be affiliated with Recall.ai the company; see the grey
  area above on a possibly-conflated "Nick from Recall.ai" reference dated 2026-06-25.
- **Carter Razink**: physics and math background, serial founder, ex-CTO of a stablecoin-rewards company,
  `carter@raz.ink`. First confirmed 3-way call with Jarred and Nick was 2026-07-08 (68 minutes, roughly
  11:05 to 12:15 PDT). Contributed a cited case study (a 4-person team at 16x baseline output versus an
  18-person control team at 2.5x) and owns the term "Recurro" as his own separate recursive-self-improvement
  framework for engineering orgs, not the joint product's name. Possibly, but not confirmed, the same
  "Carter" referenced unconfirmed in executive-agent-gui's 2026-07-03 vision brief, and possibly, but not
  confirmed, connected to the "Carter" expected but absent from the 2026-06-19 tape.
- **Alan/Allan Marshall (Upexi CEO)**: appears in two connected but distinct workstreams involving the
  same person. First, as the subject of a separate client-facing AI deck (`allan-ai-deck`) whose content
  deliberately excludes Nick, Carter, and the underlying Agent-OS business concept ("Business concept
  (incentivized adoption platform) shapes framing only, never mentioned. No Nick/Carter names in deck,"
  per the deck's own thread, 2026-07-06). Second, and separately, as the target first pilot and investor
  for the Agent-OS concept itself, with a stated $10 to $50M appetite and a pitch meeting targeted for
  around 2026-07-17/18. These are the same person but two different, deliberately separated
  conversations; do not merge the deck content with the investor pitch.
- **Fieldy and Recall.ai are not people.** Fieldy is Jarred's wearable ambient-capture device and its
  associated pipeline. Recall.ai is a third-party meeting-bot SDK/API vendor whose product Jarred
  integrated into his own tool. Neither is a company that Nick or Carter represent, per everything found
  in this pass.
- **Name-collision landscape to keep separate from the above**: "Carter (Spree)" (CRM alias, unrelated
  contact); the internal "Carter automation-stack integration" program (skills-registry work, graduated
  2026-06-12); a Carter test-fixture name in an eval harness; a "Nick" who may or may not be a distinct
  Recall.ai employee from Nick Metzler.

## Artifacts

Capture stack, code and docs:
- `/Users/jarredwinn/Projects/claudecode-bar/main.swift`, `hud.html` (Recall tile, live transcript panel)
- `/Users/jarredwinn/Projects/claudecode-bar/SECURITY-PERF-AUDIT-PLAN.md` (base64 hardening, atomic-write
  debt, dead "Launch Recall Notetaker" button)
- `/Users/jarredwinn/Projects/claudecode-bar/docs/recall-docs-panel-plan.md`,
  `docs/recall-spike-contract.md` (the unrelated local smart-search "Recall" panel)
- `/Users/jarredwinn/Projects/claudecode-bar/memory-bank/activeContext.md`
- claudecode-bar commits: `cf3fc9e` (recall panel live-scroll fix, 2026-07-07), `37afbe5` (poll transcript
  1s), `d7f6eb6` (restore Recall tile after autosync clobber)
- `mini:/Users/clawd/.openclaw/workspace/scripts/recall-bridge/recall-bridge.py`
- `/Users/jarredwinn/Projects/fieldy-clawdia/` (whole repo): `memory-bank/projectbrief.md`,
  `memory-bank/activeContext.md`, `memory-bank/lessons.md`, `memory-bank/progress.md`,
  `STACK-REEVALUATION-2026-05-21.md`, `STACK-FIX-2026-05-22-business-meeting-loss.md`,
  `TRANSCRIPT-SYSTEM-ASSESSMENT-2026-06-04.md`, `docs/speaker-identification-rethink.md`,
  `docs/finish-plan.md`, `memory-bank/decisions/0011-granola-poll-ingest.md`,
  `0012-meeting-level-speaker-presence-model.md`, `0013-per-utterance-turn-attribution.md`,
  `0014-roam-webhook-ingest.md`, `tooling/speaker-presence.py`, `tooling/turn-attribute.py`,
  `tooling/fieldy-crm-sync.py`
- `/Users/jarredwinn/Projects/brain/docs/architecture.md`, `docs/related-repos.md`,
  `memory-bank/activeContext.md`
- `/Users/jarredwinn/Projects/clawdia-atlas/docs/03-meeting-ingest-pipeline.md`,
  `04-tooling.md`, `06-processes-and-crons.md`, `07-infrastructure.md`, `08-runbooks.md`,
  `09-open-questions-and-conflicts.md`, `reference/glossary.md`, `diagrams/stack-overview.md`
- `/Users/jarredwinn/Projects/knowledge/INDEX.md`,
  `2-areas/machine-organization/RETRIEVAL-ARCHITECTURE.md`
- `mini:~/.openclaw/workspace/scripts/` (fieldy-conversation-sync.py, fieldy-meeting-detector.py,
  fieldy-tasks-to-notion.py, fieldy-crm-sync.py, fieldy-tasks-shadow.py and wrapper; named in this task's
  own brief, and consistent with, though not all individually re-confirmed against, the sibling copies
  a reader found at `mini:~/.openclaw/workspace/scripts/fieldy/fieldy_to_clickup.py` and
  `meeting_extractor.py`)
- `mini:~/.gbrain/sync-failures.jsonl`
- `mini:~/.openclaw/workspace/fieldy/transcripts/2026-07-08.jsonl` (149KB, 126 lines, raw verbatim of
  today's call)
- `https://us-west-2.recall.ai/dashboard`

Today's call and its 3x capture:
- `mini:~/.openclaw/workspace/meetings/2026-07-08-jarred-nick-carter-ai-productivity-os-gamification-ideation-9f36bc52.md`
  (fieldy-extracted, created 12:21 PT)
- `mini:~/.openclaw/workspace/meetings/2026-07-08-agentic-org-os-rsi-for-orgs-jarred-carter-nick-strategy-call.md`
  (recall, created 12:12/12:21 PT depending on reader)
- `mini:~/.openclaw/workspace/meetings/2026-07-08-jarred-nick-metzler-carter-razink-ai-gamification-enterprise.md`
  (recall, created 11:25 PT)
- `/Users/jarredwinn/.omnara/worktrees/miscellaneous/knelt-smugness/threads/2026-07-08-agent-os-product-concept-consolidation.md`
  (the authoritative local thread for this call, including Jarred's corrections)

Identity and disambiguation sources:
- `/Users/jarredwinn/Projects/executive-agent-gui/research/vision-brief.md` (unconfirmed "Carter";
  the adjacent "Nick track")
- `/Users/jarredwinn/Projects/miscellaneous/research/inbox/2026-06-19-fieldy-vision-distilled.md` and
  `threads/2026-06-19-lifeos-theory-design.md` (the absent "Carter" on the 2026-06-19 tape)
- `/Users/jarredwinn/Projects/miscellaneous/threads/_filed/automation-program/2026-06-09-carter-automation-stack-integration.md`
  (the unrelated internal "Carter" automation program)
- `mini:/Users/clawd/.openclaw/workspace/scripts/mempalace-crm-unify.py:565` ("Carter (Spree)" alias)

Reliability, competitive eviction, and client deck:
- `/Users/jarredwinn/Projects/miscellaneous/threads/2026-06-28-recall-roam-capture-brain-tile-effectiveness-loop.md`
- `/Users/jarredwinn/Projects/miscellaneous/threads/2026-06-30-recall-meet-no-mic.md`
- `/Users/jarredwinn/Projects/miscellaneous/threads/2026-07-01-yesterdays-conversations-review.md`
- `/Users/jarredwinn/Projects/miscellaneous/threads/2026-07-02-fieldy-clawdia-session-intake-failures.md`
- `/Users/jarredwinn/Projects/miscellaneous/threads/2026-07-06-recall-notetaker-not-working.md`
- `/Users/jarredwinn/Projects/miscellaneous/threads/2026-07-07-recall-panel-not-live-scrolling.md`
- `/Users/jarredwinn/Projects/miscellaneous/threads/2026-07-06-winn-ai-notetaker-stop.md`
- `/Users/jarredwinn/Projects/miscellaneous/threads/2026-07-07-winn-ai-bot-meet-anchorage.md`
- This repo's own git log: commit `9376e121` ("Winn.ai bot resolved, access cut across Google/Zoom/
  Zoom-AI"), commit `881dcde8` ("Zoom AI: disabled account-wide auto-start meeting summary; ClickUp
  removed from Marketplace"), commit `b4451906` (lesson on "bot-eviction-by-elimination")
- `/Users/jarredwinn/Projects/miscellaneous/threads/2026-07-06-allan-marshall-ai-deck.md`
- `/Users/jarredwinn/Projects/miscellaneous/allan-ai-deck/deck.html`, `talk-track.md`
- `https://winnsolutionsadmin.github.io/allan-ai-demos/`
- `/Users/jarredwinn/Projects/anchorage-workspace/99-source/meetings-full/openclaw/*fieldy-meeting*.md`
  (7 Fieldy-tagged meeting notes wired into the Anchorage CRM workspace, 2026-04-09 to 04-22)

Sibling dossiers in this same swarm sweep (not read for this pass, listed for cross-reference):
- `research/inbox/product-sweep-2026-07-08/mima-mini-corpus.md`
- `research/inbox/product-sweep-2026-07-08/swarm-allan-marshall.md`
- `research/inbox/product-sweep-2026-07-08/swarm-gui.md`
- `research/inbox/product-sweep-2026-07-08/swarm-mima.md`

## Timeline of key moments

- **2026-05-13**: Decision to keep Otter running permanently alongside Fieldy, specifically because it
  has a different vendor/STT/failure mode.
- **2026-05-21**: Founding SLO goal for the pipeline set; STACK-REEVALUATION names Limitless and
  Omi/Friend as the only competitive comparables at the time; Fieldy noted to run on Qdrant internally.
- **2026-05-22**: Real business meetings found silently dropped while family chatter was stored as
  "meetings." Jarred's directive: capture everything, filter family chatter, categorize business,
  make it accurate.
- **2026-05-27 to approx. 2026-06-06**: Otter, at the time the canonical CRM's only historical feeder,
  goes fully silent for about 10 days, freezing the canonical CRM.
- **2026-06-04**: Transcript/retrieval system assessed as "~85% built and adequate" (343 processed notes,
  298 structured JSON records, 47,397 embeddings).
- **2026-06-09**: Canonical retrieval order for a past meeting documented (calendar first, then Fieldy
  JSONL, then `data/meetings/<id>.json`).
- **2026-06-11**: A `/recall` skill is noted to query gbrain, not raw transcripts, a naming collision
  flagged even before the Recall.ai integration existed.
- **2026-06-16**: Speaker-identification root cause documented: Fieldy transcript bundles carry no
  speaker field at all; the signal exists upstream in Fieldy's own API but is discarded before reaching
  the bundle. `brain/docs/architecture.md` snapshot of the whole pipeline dated here too.
- **2026-06-16**: Decision 0012, the meeting-level speaker presence model, built and validated, not
  deployed.
- **2026-06-17**: Decision 0013, per-utterance turn attribution, built and validated for 2-person calls,
  degrades on group calls, not deployed. Granola and Roam sources added around this window, synthetic-only
  verification.
- **2026-06-19**: The core "life-OS" product vision distilled directly from a Fieldy-recorded meeting
  transcript. Same call: an expected "Carter" does not appear on tape.
- **2026-06-22**: Fieldy false-flagged as stalled by a monitoring bug that didn't account for its
  legitimate up-to-7-day offline window.
- **2026-06-25**: Jarred's record-on-detection design decision made. Separately, a "Nick" (per one
  reader's contested reading, possibly a different Nick) gives a live Recall.ai desktop-SDK demo,
  per mini's `crm/interactions/nick.md`.
- **2026-06-26 to 2026-07-02**: `recall-bridge.py` under active development on mini (per file mtimes).
- **2026-06-28**: Recall notetaker rebuilt and shipped: async transcription for real speaker names,
  native realtime streaming, live in-bar transcript, and Roam capture solved via CoreAudio per-process
  mic attribution. "Make meetings pay off" named as the biggest deferred ROI lever, not yet built.
- **2026-06-29**: Lessons captured that Recall and Granola are two separate pipelines both feeding gbrain,
  and that Recall's live in-meeting transcript feed is unreliable even though its async path works well.
- **2026-06-30**: Installing Recall breaks Chrome's mic via a macOS TCC re-evaluation (fixed same
  session). A Nick Metzler call is double-ingested by both Otter and Recall with different dedup keys.
- **2026-07-01**: Nick follow-up locked for 2026-07-03. `fieldy_to_clickup.py` armed in shadow mode, live
  proof of 5 tasks extracted from a real meeting. Record-on-detection reaffirmed as accepted cost, not to
  be revisited.
- **2026-07-02**: Fieldy device stops uploading. Separately and more seriously, gbrain sync is found to
  have silently dropped every meeting since 2026-06-30 due to OpenAI embedding-quota exhaustion combined
  with a `--skip-failed` flag masking the errors; a reconciler safety net had been disabled for 41 days;
  an estate-wide sweep finds 275 historical files dropped in total, 7 still missing (including Anchorage
  deal context).
- **2026-07-03**: Executive-agent-gui repo scaffolded the same day as a second Nick meeting (2pm ET).
  Vision brief for that repo flags an unconfirmed "Carter" and an adjacent "Nick track" (gamified
  enterprise adoption concept).
- **2026-07-05**: `gui-relay` skill confirmed as unrelated hardware-input tooling, ruling it out as any
  kind of product codename.
- **2026-07-06**: Recall notetaker found not working; root cause was a disabled launchd job, fixed same
  session, with heartbeat monitoring added afterward. A ClickUp board task, "Decide between Jamie AI and
  Recall.ai speaker attribution path," is noted as separately open. The Allan Marshall deck's thread
  explicitly excludes Nick, Carter, and the business concept from that client-facing deck. The Winn.ai
  (Read AI) notetaker-eviction thread begins.
- **2026-07-07**: Recall panel's live-scroll bug fixed (commit `cf3fc9e`). The Winn.ai/Fireflies eviction
  from Anchorage's Zoom and Google Workspace completed, confirmed by this repo's own commits `9376e121`
  and `881dcde8`; Recall's own bot API was queried directly and returned 0 active bots, used as evidence
  in ruling Recall out as the source of the unwanted bot.
- **2026-07-08**: First 3-way call between Jarred, Nick Metzler, and Carter Razink, 68 minutes, roughly
  11:05 to 12:15 PDT, on a gamified Agent OS / RSI-for-orgs concept. Captured three times by the capture
  stack (once fieldy-extracted, twice via Recall) plus one raw transcript. Jarred issues two authoritative
  corrections afterward: mima is unrelated to this concept, and "Recurro" is Carter's own separate term,
  not the joint product's name. Per this task's own goal context (not independently re-verified here),
  gbrain's embedding pipeline is again reporting quota exhaustion as of this morning, meaning today's
  three meeting notes are likely not yet semantically indexed.

## Sources

- `threads/2026-07-08-agent-os-product-concept-consolidation.md` (2026-07-08; read directly for this
  dossier; the authoritative primary source for today's call and Jarred's corrections)
- `executive-agent-gui/research/vision-brief.md` (compiled 2026-07-03, covering 2026-06-19 to 2026-07-03;
  read directly for this dossier)
- `miscellaneous/threads/2026-07-06-recall-notetaker-not-working.md` (2026-07-06; read directly for this
  dossier)
- `fieldy-clawdia/memory-bank/projectbrief.md` (2026-05-21), `STACK-REEVALUATION-2026-05-21.md`,
  `STACK-FIX-2026-05-22-business-meeting-loss.md` (2026-05-22),
  `TRANSCRIPT-SYSTEM-ASSESSMENT-2026-06-04.md` (2026-06-04), `docs/speaker-identification-rethink.md`
  (2026-06-16), `memory-bank/decisions/0012-*.md` (2026-06-16), `0013-*.md` (2026-06-17),
  `memory-bank/activeContext.md` and `lessons.md` (entries through 2026-06-17/19), `docs/finish-plan.md`
- `brain/docs/architecture.md`, `docs/related-repos.md`, `memory-bank/activeContext.md` (snapshot dated
  2026-06-16)
- `clawdia-atlas/docs/03-meeting-ingest-pipeline.md` and related docs (last verified/committed
  2026-06-15/19)
- `knowledge/INDEX.md`, `2-areas/machine-organization/RETRIEVAL-ARCHITECTURE.md` (assessed 2026-06-04,
  added 2026-06-04)
- `claudecode-bar/main.swift`, `hud.html`, `SECURITY-PERF-AUDIT-PLAN.md`, `docs/recall-docs-panel-plan.md`,
  `docs/recall-spike-contract.md` (verified 2026-06-19, panel graduated 2026-06-26, live-scroll fix
  2026-07-07)
- `miscellaneous/research/inbox/2026-06-19-fieldy-vision-distilled.md` and
  `threads/2026-06-19-lifeos-theory-design.md` (2026-06-19)
- `miscellaneous/threads/2026-06-28-recall-roam-capture-brain-tile-effectiveness-loop.md` (2026-06-28),
  `2026-06-30-recall-meet-no-mic.md` (2026-06-30), `2026-07-01-yesterdays-conversations-review.md`
  (2026-07-01, reviewing 2026-06-30), `2026-07-02-fieldy-clawdia-session-intake-failures.md` (2026-07-02),
  `2026-07-07-recall-panel-not-live-scrolling.md` (2026-07-07), `2026-07-06-winn-ai-notetaker-stop.md`
  and `2026-07-07-winn-ai-bot-meet-anchorage.md` (2026-07-06/07)
- `miscellaneous/threads/2026-07-06-allan-marshall-ai-deck.md` (2026-07-06), `allan-ai-deck/deck.html`
  and `talk-track.md` (2026-07-06/07)
- `miscellaneous/threads/_filed/automation-program/2026-06-09-carter-automation-stack-integration.md`
  (2026-06-09/12)
- `miscellaneous/org/objective-ledger.yaml` and `the-sage/goals/goals.json` (goals.json last updated per
  its own header 2026-06-22)
- This repo's git log: commits `9376e121`, `881dcde8` (both 2026-07-07), `b4451906`
- Negative checks (confirmed no relevant content): `command-center`, `teamclaude-fleet` repos;
  `miscellaneous/threads/_filed/executive-agent-gui/README.md`; `miscellaneous/DEBRIEF.md` (unrelated
  Agent Browser Viewer project); `/private/tmp/mima_story_v3.pdf` (no meeting-capture content, confirming
  meeting capture is not part of mima's original lineage); `gui-relay` skill (unrelated hardware tooling)

## Confidence notes

**Solid, directly sourced:**
- The core identity resolution (Nick Metzler and Carter Razink, not a "Fieldy/Recall company"; Recurro as
  Carter's own term, not the joint product's name; mima as unrelated) rests on a direct read of the
  primary 2026-07-08 thread, which states these as Jarred's own authoritative corrections. This is the
  highest-confidence material in this dossier.
- The two-track architecture (documented Otter/Fieldy/Granola/Roam pipeline versus the separately-built
  Recall.ai integration) is confirmed by four independent readers each grepping a different repo
  (fieldy-clawdia, brain, clawdia-atlas, plus a fourth cross-check) and each finding zero mentions of
  Recall.ai in the "official" architecture docs. This convergence across independent passes makes it
  solid.
- The speaker-attribution root cause (no speaker field in Fieldy's transcript bundles despite the signal
  existing upstream), the presence-model and turn-attribution decisions, and their "not deployed" status
  are all drawn from dated ADR-style decision docs with quoted evidence, not inference.
- The reliability/data-loss track record (2026-05-22 through 2026-07-02) is drawn from dated incident
  writeups with quoted root causes and is consistent across readers.
- The Winn.ai/Fireflies eviction and its resolution is corroborated by this repo's own git log, which is
  about as solid a source as is available in this environment.
- The Allan Marshall deck's value-proposition language is drawn from direct deck/talk-track quotes.

**Thinner, flagged explicitly above but worth restating together:**
- The "Nick from Recall.ai" versus "Nick Metzler" question rests on one reader's reading of a merged CRM
  file and was not independently re-opened in this pass.
- The link between the unconfirmed "Carter" in executive-agent-gui's vision brief (2026-07-03) and Carter
  Razink (confirmed 2026-07-08) is plausible on timing and thematic grounds (the same document's "Nick
  track" matches the gamification theme) but is explicitly not confirmed by that document itself, and no
  later document closes the loop.
- Whether the absent "Carter" on the 2026-06-19 tape is connected to Carter Razink is unknown; it may be
  entirely unrelated given how overloaded the name "Carter" is elsewhere in this estate.
- Today's (2026-07-08) gbrain quota-exhaustion status and the exact creation timestamps of the three
  meeting-note captures come from this task's own goal context rather than from this pass's own reader
  findings or direct verification, and should be read as reported, not independently confirmed here.
- The open "Jamie AI vs Recall.ai" board task has no visible detail beyond its title in any corpus
  checked; its current status should be pulled from ClickUp directly if it matters downstream.
- No competitive analysis of Recall.ai against other notetaker vendors exists in any source found; this
  dossier can only confirm the gap, not fill it.
