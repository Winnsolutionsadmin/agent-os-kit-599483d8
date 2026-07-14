# Architecture Overview: System Map (09-infra artifact 1 of 5)

**Authored:** 2026-07-08, infra-clickup session
**Product:** UNNAMED (Agent OS is a descriptor). Founder: Jarred Winn. Positioning: trusted companion through the AI transition.
**Sources:** 01-overview v2 (pillars, scorecard, must-haves), 03-execution/architecture-consolidation.md, 03-execution/enterprise-deployment.md (both carry Upexi-invalidity caveats; only their architecture content is used here), 07-roadmap W3/W4/W5/W9 decided scope, counsel verdicts 2026-07-08.
**Precedence:** where this file conflicts with the inherited 09-infra/INFRA-STRATEGY.md draft, THIS file and build-sequence.md govern (see README).
**Lineage legend:** MEASURED / SURVEY / VENDOR / [unverified].

---

## 1. Governing design facts

1. **Nothing in the estate is multi-tenant-shaped** (MEASURED, repo-reality scan 2026-07-08). Three of four core pillars carry validated logic worth consolidating as libraries, not rewriting: the-sage OKR scoring (99.3% alignment on 275/277 commits, MEASURED), the capture pipeline (343 processed notes, 47k embeddings, MEASURED), the achievement-engine math (live since 2026-04-19, 23-day streak, MEASURED). The front door is the one pillar with no shipping code to consolidate; it gets built new.
2. **Product law is an architectural invariant, not a feature:** zero ungated money / irreversible / external actions; autonomy only via graduation (90% agreement over 20+ reps per decision class). Counsel: "don't touch it." Enforcement design lives in product-law-enforcement.md.
3. **Split front door from operator console.** The client-facing surface is a new multi-tenant web app (SAML/OIDC redirect SSO; OAuth in embedded webviews violates RFC 8252). The native operator console (claudecode-bar lineage) stays internal. The two-pane pattern, Approve/Edit/Skip cards, and graduated-autonomy rule migrate as patterns; the code does not.
4. **W3 founder decision (2026-07-08): the pre-7/15 spike is a live READ-ONLY estate readout.** No live action paths in the room. The two-pane UI pattern is estate IP; the Mima venture is excluded and never referenced.
5. **ClickUp is the first backbone, behind an adapter, public API plane only.** The internal-frontdoor JWT technique is ToS-gray and never ships against client workspaces (estate capability map, 2026-06-18). Counsel verdict 7: design the PM-tool-agnostic interface now; build the second connector (Linear, the more agent-native candidate as a named MCP Enterprise-Managed Authorization adopter, VENDOR/press) only when a design partner requires it.
6. **Platform hedges are engineering hygiene, not existential posture** (decision 0003). Frontier-lab capability is the market premise. Hedge set: multi-model abstraction (LiteLLM-class, self-hosted), quarterly open-weight fire drill, ZDR + output-ownership in writing, Bedrock/Vertex as a procurement lever for risk-averse buyers. Sovereign GPU stack explicitly deferred; only as a client-funded line item if a contract requires it.

## 2. System map

```
                          +--------------------------------------+
                          |  FRONT DOOR (client surface)         |
                          |  read-only answer relay first (W3);  |
                          |  two-pane: conversation + workspace; |
                          |  Approve/Edit/Skip decision cards    |
                          +-------------------+------------------+
                                              |
             +--------------------------------+---------------------------------+
             |                                |                                 |
   +---------v---------+          +-----------v-----------+          +----------v---------+
   |  GATE SERVICE     |          |  ORCHESTRATION LAYER  |          |  EVENT BUS         |
   |  decision-class   |<-------->|  agent fleet sessions |--------->|  one stream, three |
   |  registry +       |          |  (Agent SDK + MCP     |          |  consumers: W8     |
   |  graduation ledger|          |  connectors; LiteLLM  |          |  thresholds, W10   |
   |  + immutable audit|          |  model abstraction)   |          |  ledger, W4 scores |
   +---------+---------+          +-----+-----------+-----+          +----------+---------+
             |                          |           |                           |
   +---------v---------+   +------------v--+   +----v-------------+   +--------v----------+
   | CAPTURE PIPELINE  |   | OKR ENGINE    |   | PM-TOOL ADAPTER  |   | ACHIEVEMENT +     |
   | meeting -> memory |   | org tree ->   |   | ClickUp first    |   | GAMIFICATION      |
   | (fieldy/recall    |   | weighted agent|   | (public API);    |   | rarity x impact;  |
   | consolidated libs)|   | subtasks ->   |   | Linear on partner|   | leagues/anti-abuse|
   |                   |   | outcome score |   | demand           |   | post-Nick 7/31    |
   +-------------------+   +---------------+   +------------------+   +-------------------+
                                              |
                          +-------------------v------------------+
                          | TENANT + GOVERNANCE SUBSTRATE (W9)   |
                          | isolation, consent, retention,       |
                          | logging; SOC2-aligned controls now   |
                          +--------------------------------------+
```

## 3. Component specifications

### 3.1 Front door (W3 scope)
- **Phase 0 (pre-7/15):** exec-gui answer-relay spike, read-only, wired to ONE real estate surface (fleet HUD or OKR readout). Demo script = W3.4, founder-reviewed.
- **V1 (pilot through month 2-4):** new multi-tenant web app. Conversation pane + modular workspace pane; intent bar promotion actions (Ask / Save as idea / Convert to task / Save as workflow / Build it now); Approve/Edit/Skip triage cards; native decision cards relaying answers into live agent sessions. Executive-translator quality floor: Sonnet-class or better (Haiku explicitly rejected, must-have 12). Calm by default; only the one thing that needs the human pulses (must-have 8).
- **Auth:** SAML/OIDC redirect SSO in the browser. Never OAuth in an embedded webview.
- **Operator console:** claudecode-bar stays the internal fleet HUD; patterns exported, code not ported.

### 3.2 Meeting / capture pipeline
- Consolidate fieldy-clawdia + recall-notetaker behind a service boundary; do NOT rewrite extraction logic ("~85% built, do NOT rebuild" is Jarred's own assessment, [unverified] as a productization estimate; the live dedup bug says the remaining gap may exceed 15%).
- **Pre-second-tenant blockers:** fix capture dedup (the 7/8 call landed 3x, MEASURED); sanctioned-capture-only discipline (must-have 7, the Winn.ai eviction lesson); silence must look like breakage (must-have 22; E3 capture-missed is incident-grade).
- Speaker attribution deploys only with the Clarify rung (flags ambiguity, never guesses; must-have 5) and only under the W9 consent posture (active wiretap/BIPA litigation risk against this feature class, see data-governance-architecture.md).
- Hard wall: legal, board, and M&A meetings excluded from capture by policy before any regulated-client pilot.

### 3.3 OKR engine (W5 scope, generalized from the-sage)
- Carry the validated core: goals schema (North Star -> Driver -> KR) + score_alignment() as a library. Wrap with per-tenant isolation; do not rewrite scoring logic.
- Build order (W5 backlog): document the-sage as it runs -> org-shaped multi-tenant tree schema -> weighted agent-subtask mapping (OKR node -> agent tasks -> weights) -> outcome scoring spec (feeds W4, comp-decoupled).
- Activity-alignment ships first; outcome-movement is the real axis and needs a real KR data source before any score is more than a vanity metric (must-have 17).

### 3.4 Achievement / recognition engine + gamification layer
- Achievement engine generalizes the mini engine (points = rarity x impact, 4 tiers, common-tier silenced). Per-person/per-org data model is a genuine rebuild and is BLOCKED on Nick's 7/31 mechanics spec; do not start early and build it twice.
- Anti-abuse primitives from day one (must-have 15): leagues, daily caps ("90% never hit the cap, analyze the ones that do"), outlier detection, consistency gating, role-adjusted scoring. Nick is author of record; this repo synthesizes.
- **Comp-decoupled at the code level:** no data path from scores to compensation systems. Opt-in per feature (E15). Enters at pilot day 31 only after the day-30 evidence gate.

### 3.5 Attribution pillar
- Future wedge, ZERO build now (counsel verdict 10: a zero-build pillar must not anchor the whitespace claim). The immutable audit log (product-law-enforcement.md section 4) is designed so its event shape can later serve proof-of-origination without rework: every event already carries initiator, approver, executor, timestamps.

### 3.6 Agent fleet orchestration
- Substrate: Claude Agent SDK + MCP for tool connectors. What the SDK does NOT provide and we must build (VENDOR, SDK docs + 2026 production guides): retries, per-tenant budget caps, durable execution, centralized observability, multi-tenancy. These are the real V1 engineering lift; pai-observatory and teamclaude-fleet are the estate's own prior recognition of exactly this gap list.
- Session context carries tenant + user + decision-class scope; agent-initiated actions route through the gate service without exception.
- Untrusted-content discipline (must-have 6): transcripts and meeting text are externally-influenced input, isolated from execution paths.

### 3.7 PM-tool adapter interface (design now, per counsel verdict 7)
- Interface surface: tasks CRUD, goal/KR read-write, webhooks-in, status sync, idempotent upserts keyed by external id.
- ClickUp connector first (public API plane only; workspace-scope webhooks filtered client-side). Linear connector when a design partner requires it. No product logic ever imports a vendor SDK directly; everything goes through the adapter.

### 3.8 Multi-model abstraction + credential hygiene (platform hedge as hygiene)
- LiteLLM-class self-hosted proxy from the first product commit; prompts and tool schemas kept vendor-portable where it does not cost quality. Quarterly fire drill against one open-weight model; the drill is what makes the hedge real (enterprise-deployment.md risk note).
- **OAuth/API-key audit (near-term, mechanical):** verify which estate automation runs on consumer OAuth vs proper API keys. Anthropic enforced against consumer-OAuth tooling in January 2026 (VENDOR/press); commercial/production use requires API-key auth. This is cheaper than any other risk retirement on this list.
- ZDR + output-ownership requested in writing; note the Covered-Models carve-out (Fable/Mythos class: no ZDR, mandatory 30-day retention, VENDOR terms) so the "zero retention" assumption never breaks silently.

### 3.9 Tenant + governance substrate
- Summarized here, specified in data-governance-architecture.md: pilot phase = single-partner segregated deployment; V1 = schema-per-tenant Postgres + row-level security + per-tenant keys. Partner event data segregated from the reference-implementation estate from day 1.

## 4. Whitespace and threat-read constraints (from 04-competitive)

- The occupied category: OKR-scoring + gamification + attribution stack with consulting delivery. The threat read (2-of-7 pillars commoditized: front-door GUI and plugin/skill marketplace are already shipping in Claude Cowork, VENDOR/press 2026) must always be presented reconciled with the whitespace claim, never as independent facts.
- Consequence for architecture: differentiation concentrates in the OKR-outcome loop, the gamified adoption layer, the graduation-trust machinery, and per-org data compounding. The front door is necessary but not defensible; build it lean.

## 5. Needs founder

1. Confirmation that the E9 "edit = disagreement" conservative graduation read is the product rule (carried from instrumentation-spec open item 3).
2. Front-door V1 web-vs-native-wrapper final call when the first paying client's IT posture is known (architecture-consolidation recommends web + optional Tauri shell; an enterprise Conditional-Access requirement would flip it to Electron).
3. Timing of the OAuth/API-key estate audit (recommended: before first partner data flows).
