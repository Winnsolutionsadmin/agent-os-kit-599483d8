# End-to-End Infrastructure and Build Strategy

**Product:** Unnamed gamified AI-powered organizational operating system  
**Founder:** Jarred Winn  
**Originating members:** Nick Metzler, Carter Razink (earn equity through contribution)  
**Document date:** 2026-07-08  
**Scope:** Full build strategy for all seven pillars + supporting infrastructure

---

## I. Strategic Foundation

### Vision Statement
Compress the time between thought and output by providing a calm conversational surface through which any employee directs agent work, with adoption driven by game mechanics that reward AI adoption instead of threatening replacement.

### Core Constraints (Product Law)
1. **Human gates on high-impact decisions:** Never auto-act on money, irreversible actions, or external impacts without human approval
2. **Graduation rule:** Agents earn autonomy via 90%+ agreement over 20+ identical decision classes
3. **Transparent design:** Product must be auditable, with attribution and provenance built in
4. **No forcing functions:** Gamification decoupled from compensation to prevent backlash

### Positioning
The trusted companion that brings companies through the AI transition and gives them a head start. We acknowledge that frontier labs (Anthropic, OpenAI, Google) have the capability; we occupy the space of trusted implementation, consulting delivery, and enterprise relationships.

### Domino GTM (Founder-ordered)
1. **C-level chief of staff / organizer** (wedge into executive function)
2. **Engineers** (demand-driven revamp of development workflows)
3. **Organization-wide** (based on proven demand)

---

## II. Architecture: Seven Pillars

### Pillar 1: Front-Door GUI
**Requirement:** Single calm conversational surface for all org interactions  
**Evidence:** 4 demo patterns exist (triage.html, imessage.html, fleet.html, treasury.html); claudecode-bar estates the production HUD

**V1 Buildout:**
- Two-pane layout: persistent conversation pane (left) + modular workspace pane (right)
- Intent bar with four promotion actions: Ask (to agent) / Save as idea / Convert to task / Build it now
- Approve/Edit/Skip triage cards for incoming items
- Native decision cards that relay answers back to live agent sessions
- Click-to-debug session spawning (launch pre-briefed sessions on any item)
- Session search/recall panel (8-10s -> 0.06s Recall.ai SDK integration)

**Technology:**
- Frontend framework: React or web components (estate currently React)
- Real-time: WebSocket or polling to agent session streams
- State management: Whatever patterns claudecode-bar establishes (store + hydration layer)
- Desktop app: Tauri or Electron for macOS/Linux/Windows fleet HUD integration

**Dependencies:**
- Agent session architecture stable (RFC from agent-os team)
- Multi-tenant permissions layer (who sees what, per role/org)
- Conversation history/embedding search

**Target shipping:** Pre-7/15 spike for live demo; V1 (multi-user, cross-org) by day 30 post-pilot

### Pillar 2: OKR Engine
**Requirement:** Org-level OKRs -> weighted agent subtasks -> outcome scoring  
**Evidence:** the-sage pattern in production on single operator; score_alignment() achieves 99.3% on 277 commits

**V1 Buildout:**
- Goals schema: North Star -> Driver -> Key Result -> weighted subtasks
- Org model: Multi-tenant OKR tree with per-org customization
- Agent integration: Every agent task scored against its parent OKR for alignment
- Outcome movement: Real success metric (not just activity alignment)
- PM tool abstraction: Generalize the-sage pattern to consume from ClickUp/Linear/Jira APIs
- Scoring model: Outcome points = (KR weight) x (task completion %) x (quality multiplier)

**Technology:**
- OKR storage: Postgres + jsonb for schema flexibility
- Integration layer: PM-tool-agnostic adapter interface (ClickUp first, Linear on demand)
- Scoring engine: Python + async workers for daily scoring runs
- Dashboard: Real-time OKR heatmap (green/yellow/red progress indicators)

**Dependencies:**
- Multi-tenant data isolation (W9)
- Agent task API (what defines a "task" in the system)
- PM tool connector architecture (adapter pattern)

**Target shipping:** Month 1 (domain logic), Month 2 (multi-tenant hardening)

### Pillar 3: Gamification + Anti-Abuse
**Requirement:** Points, tiers, streaks, leagues with anti-abuse controls; comp-decoupled  
**Evidence:** Mini achievement engine live since 2026-04-19 (5027 pts, 23-day streak); Nick has anti-abuse mechanics design

**V1 Buildout:**
- Scoring model: Rarity (event class) x impact (outcome delta) x multiplier (context)
- 4-tier system: Common (silenced) / Uncommon / Rare / Legendary
- Streaks: Longest unbroken chain per event class + combo multipliers
- Leagues: Org-level leaderboards with role-adjusted scoring
- Anti-abuse: Minimum daily thresholds + hard caps (e.g., 90% of orgs never exceed), outlier detection, honeypots
- Compensation isolation: Points system and comp are separate; comp never tied to gamification scores
- Opt-in posture: All gamification features default off; pilot participants opt in per feature

**Technology:**
- Event ingestion: Stream all product actions (agents, decisions, commits, approvals)
- Scoring engine: Rule engine + async scoring workers
- Leaderboard service: Redis-backed real-time aggregation
- Anti-abuse module: Anomaly detection (statistical + ML-based)
- UI: Achievement panel in front-door GUI, weekly digest email

**Dependencies:**
- Comprehensive event instrumentation (every action emits an event)
- User/org/role hierarchy (who competes with whom)
- Compensation system (integration point, but decoupled at code level)

**Target shipping:** Pilot phase 1 (day 30 hand-off), hardening Month 1-2

### Pillar 4: Meeting Capture + Intelligence
**Requirement:** Auto-join + transcription + CRM/action extraction + memory  
**Evidence:** fieldy-clawdia pipeline (40 scripts, 343 notes, 47k embeddings); recall-notetaker working; fieldy-to-ClickUp in shadow mode

**V1 Buildout:**
- Transcription: Otter + Fieldy with vendor redundancy for accuracy
- Auto-join: Recall.ai SDK for Zoom/Teams/Calendar integration
- Metadata: Speaker attribution (turn-level, validated 0.90+ accuracy)
- CRM sync: Automatic contact tagging + org extraction
- Action items: NLP-based extraction + auto-routing to owners
- Memory: Embedding-based retrieval (LangChain + Pinecone or Postgres pgvector)
- Decision logging: Explicit decision capture linked to action items
- Privacy: 3-tier classification (business/topical/personal-quarantined)

**Technology:**
- Transcription: Otter API + fallback to AssemblyAI or Deepgram
- Auto-join: Recall.ai SDK + calendar integration (Google/Outlook)
- NLP: Llama 2 70B or Claude for extraction (accuracy/cost tradeoff)
- Embeddings: all-MiniLM-L6-v2 (local) or Voyage AI (cloud)
- Storage: Postgres for structured, S3 for audio/transcripts
- CRM: Sync to Salesforce/HubSpot APIs, LLM gate on contact creation

**Dependencies:**
- Recording consent + GDPR/SOC2 compliance
- Speaker identity service (who is talking?)
- Agent session context (which meeting relates to which OKR/task?)

**Target shipping:** Day 1 of pilot (capture only); action extraction by day 15

### Pillar 5: Client Relationships + Delivery
**Requirement:** Consultative engagement machine that lands software inside companies  
**Evidence:** 6+ active clients, /newclient Drive scaffold, per-client style guides, feedback registries

**V1 Buildout:**
- Engagement scaffold: Pattern onboarding + kickoff + review cadence
- Client feedback registry: Structured feedback gates content generation
- Style guides: Per-client voice/tone/terminology rules
- Review queue: Approval bottleneck in front-door GUI (organized by client)
- Success metrics: OKR alignment + CFO ROI model + NPS tracking
- White-glove service: Jarred + originating members on initial pilots

**Technology:**
- CRM: Salesforce or HubSpot for relationship tracking
- Document collaboration: Google Drive + custom Drive API integration
- Feedback system: Structured forms + Postgres + tag-based filtering
- Review queue: Channel in the front-door GUI (same triage pattern as agent approvals)

**Dependencies:**
- Client data isolation (separate tenants)
- Permission model (what can a client admin do vs regular user)
- Security posture (W9: data governance)

**Target shipping:** Pilot phase 1 (manual delivery by Jarred), scalable ops by Month 2-3

### Pillar 6: Skill Marketplace (Future Wedge)
**Requirement:** Reusable workflows + skills registry + (future) monetization  
**Evidence:** 296-skill personal registry with nightly self-improver; no funded occupant in space

**V1 Buildout:**
- Skill registry schema: Name, inputs, outputs, tags, version, owner, usage stats
- Skill discovery: Search + filter by tag/category
- Skill execution: Direct invocation from intent bar or as agent sub-action
- Skill versioning: SemVer + rollback capability
- Usage attribution: Track who runs what skill and why (feeds achievement ledger)
- Monetization: Parked for Month 6+; infrastructure in place for future

**Technology:**
- Registry: Postgres + OpenAPI schema per skill
- Execution: Skill runner (agent-agnostic callable interface)
- Discovery UI: Searchable panel in front-door GUI (right pane)
- Versioning: Git-like immutable versioning + manifest schema

**Dependencies:**
- Agent task API (what is a "skill"?)
- Execution sandbox (security, cost metering, timeout handling)

**Target shipping:** Basic registry + discovery by Month 2; execution by Month 3; monetization Month 6+

### Pillar 7: Attribution + Proof of Origination (Future Wedge)
**Requirement:** Who originated ideas, who approved actions, who ran agents autonomously  
**Evidence:** Zero code; counsel says "future wedge, don't anchor whitespace on it"

**V1 Buildout:**
- Record linkage: Every action captures initiator (person), approver (person), executor (agent/person)
- Immutable log: Append-only event log with signatures
- Audit trail: Searchable chain-of-custody for ideas and decisions
- Trust score: Reputation per agent/person based on outcomes
- Governance: Zero-knowledge proofs (ZK) for high-stakes audit (Month 9+)

**Technology:**
- Log storage: Postgres WAL + S3 archive
- Signatures: Ed25519 + opaque commit SHAs
- Query interface: GraphQL or REST for compliance/audit teams
- ZK: Parked until real use case; library prep (Noir, Circom) in Month 4

**Dependencies:**
- Complete audit event instrumentation (Pillar 4 + OKR + Gamification)
- Key management (signing keys for agents)
- Legal framework (what evidence do we need?)

**Target shipping:** Basic logging by Month 2; audit UI by Month 4; ZK Month 9+

---

## III. Platform & DevOps Infrastructure

### Multi-Tenant Architecture
**Requirement:** Tenant data isolation + fair resource allocation + compliance  
**Status:** Designed; not deployed

**Strategy:**
- **Database isolation:** Postgres schema-per-tenant (cost-effective, good isolation)
- **Row-level security (RLS):** Postgres RLS policies enforce org_id filtering on all queries
- **Key management:** Tenant-specific encryption keys (cloud KMS or Vault)
- **Rate limiting:** Per-tenant API quotas + fair token allocation
- **Breach response:** Tenant-aware audit logging + compliance playbooks

### API Layer
**Requirement:** Stable agent/client surface layer  
**Stack:**
- **Framework:** FastAPI (Python) or Remix (Node); FastAPI preferred for agent ecosystem alignment
- **Authentication:** OAuth 2.0 (agency + user clients) + service accounts (agents)
- **Authorization:** RBAC (role) + ABAC (org context) via Authz library (e.g., Casbin)
- **Validation:** Pydantic + OpenAPI spec
- **Rate limiting:** Redis-backed sliding window
- **Logging:** Structured JSON to CloudWatch + Datadog

### Agent/Client Integration
**Requirement:** Safe agent execution + client authentication  
**Patterns:**
- **Agent SDK:** Minimal wrapper (init, invoke, auth) for agent code
- **Client SDK:** JavaScript/Python libraries for embed + OAuth flow
- **Callbacks:** Agent -> Product webhook pattern for approvals/feedback
- **Session context:** Agent instances carry tenant + user + OKR context

### Data Storage
**Strategy:**
- **Operational data:** Postgres (primary) + Redis (session/cache)
- **Time series:** TimescaleDB extension for OKR scoring runs + gamification events
- **Embeddings:** Postgres pgvector extension for meeting search
- **Document storage:** S3 + CloudFront CDN
- **Backups:** Daily snapshots to cross-region S3; 30-day retention

### Secrets + Key Management
**Requirement:** Zero secrets in code; audit trail on all access  
**Tools:**
- **Development:** OpenClaw (internal mini-based vault)
- **Production:** AWS Secrets Manager (EC2/ECS) or Hashicorp Vault
- **Rotation:** Automatic 90-day key rotation
- **Audit:** All secret access logged to CloudWatch

### Observability
**Stack:**
- **Metrics:** Prometheus + Grafana (self-hosted) or Datadog
- **Logs:** CloudWatch + structured JSON (tenant_id, user_id, action, duration)
- **Traces:** OpenTelemetry SDK (via PAI) + Jaeger or Datadog APM
- **Dashboards:** Golden signals (latency, error rate, throughput) per service + per-tenant
- **Alerting:** PagerDuty for p0 incidents (API errors, data loss, security events)

### CI/CD + Deployment
**Strategy:**
- **Code:** GitHub (private) + branch protection (reviews required)
- **CI:** GitHub Actions (test + lint + type check)
- **Artifact:** Docker images pushed to ECR (tagged by commit SHA)
- **CD:** GitOps (Flux or ArgoCD) for production deployments
- **Rollback:** Canary deploys (5% -> 25% -> 100%); automatic rollback on error rate spike

**Deployment environments:**
- Development (staging): Continuous deploy from `main` branch
- Production: Manual gate (founder approval) for mainline; auto-rollback on metrics triggers

### Security Posture (SOC2-Aligned)
**Controls (starting now):**
1. **Access control:** SSH keys + MFA for all infrastructure, RBAC for applications
2. **Data encryption:** AES-256 at rest, TLS 1.3 in transit
3. **Logging:** All access (system + app) logged to immutable S3 archive
4. **Vendor review:** Quarterly assessment of third-party tools (Otter, Recall, Salesforce, etc.)
5. **Incident response:** Playbook for data breach + security event disclosure
6. **Password policy:** 12+ characters + complexity; 90-day rotation for service accounts

**Formal audit:** Triggered by first enterprise deal; 9-15 month timeline (SOC2 Type II)

### Compliance + Data Governance (W9)
**Requirements:**
- **Consent:** Explicit consent for transcription + analysis (checkbox at meeting start)
- **Retention:** Auto-delete after 90 days unless explicitly archived
- **Segregation:** Meeting data, OKR data, scoring data in separate schema/tables
- **Breach response:** 24-hour internal notification + 72-hour customer notification (GDPR)
- **Surveillance risk:** Scoring data flagged as "sensitive" + governance layer (W9.3)

---

## IV. Technology Stack

### Backend Services

| Service | Purpose | Tech | Owned by |
|---------|---------|------|----------|
| API gateway | Request routing, auth, rate limiting | FastAPI + Authz | Infra team |
| OKR engine | Goal -> subtask scoring | Python + Postgres | W5 team |
| Gamification | Points, streaks, leagues, anti-abuse | Python + Redis | W4 team |
| Meeting service | Transcription, CRM sync, memory | Python + Otter SDK | Pillar 4 team |
| Skill registry | Skill CRUD + execution | FastAPI + Docker | W6 team (future) |
| Client service | Engagement tracking, style guides | FastAPI + Postgres | Pillar 5 team |
| Audit log | Immutable action log | Postgres WAL + S3 | Infra team |

### Frontend
- **Web app:** React + TypeScript + TailwindCSS (or Estate pattern)
- **Mobile:** React Native (cross-platform) or web-only initially
- **Desktop HUD:** Tauri wrapper (native window) or Electron

### Agent Integration
- **Agent language:** Python (primary) + TypeScript
- **SDK:** Claude agent SDK wrapper + custom init/invoke layer
- **Sandbox:** Docker containers per agent instance (cost/security tradeoff)

### External Integrations
- **LLM:** Claude 3.5 Sonnet (primary) + OpenAI GPT-4 (backup)
- **Meeting:** Otter.ai + Recall.ai (redundancy)
- **CRM:** Salesforce / HubSpot (APIs)
- **PM tools:** ClickUp + Linear APIs (adapter pattern)
- **Calendar:** Google Calendar + Outlook (Microsoft Graph)

---

## V. Development Workstreams & Roadmap

### Phase 1: Spike & Demo (Pre-7/15)
**W3 (Front-door):** Live read-only estate readout, answer-relay spiked
**Output:** Demo script for 7/17-18 investor meeting

### Phase 2: Design-Partner Pilot (Days 1-30)
**W7.1:** Capture + ONE gated workflow (e.g., OKR decision approval)
**W1:** Concept doc + deck finalized
**W10.2:** Achievement ledger starts accumulating

**Output:** First customer data in system; 30/60/90 success thresholds established

### Phase 3: Pilot Phase 2 (Days 31-90)
**W4:** Gamification enters (opt-in)
**W5:** OKR engine productized (org schema)
**W8/W9:** Pricing & governance finalized via customer feedback

**Output:** Proof of outcome movement (not just activity alignment)

### Phase 4: V1 Product Release (Month 3-4)
**W3:** Multi-user front-door GUI (engineering teams)
**W5:** Full OKR productization + adapter layer
**W4:** Leagues + anti-abuse hardened

**Output:** Deployable product; second design partner onboarding begins

### Phase 5: Scale & Raise (Month 4-6)
**W10:** Achievement ledger triggers investor raise (SIGNED PILOT)
**Infra:** Multi-tenant hardening + security audit begins
**Sales:** Second/third design partners via domino ladder

**Output:** Syndicate raise; team hiring begins

---

## VI. Cost Model & Economics

### Infrastructure Costs (Estimated)

| Component | Size | Monthly | Annual |
|-----------|------|---------|--------|
| Compute (EC2/ECS) | t3.medium (2-4 instances) | $200 | $2,400 |
| Database (RDS) | db.t3.micro + backups | $150 | $1,800 |
| Storage (S3) | 100GB + CloudFront | $50 | $600 |
| Third-party APIs | Otter, Recall, Salesforce | $500 | $6,000 |
| Observability (Datadog) | 3 hosts | $150 | $1,800 |
| **Total** | - | **$1,050** | **$12,600** |

### Scaling Costs
- Per-tenant: +$10/month (marginal DB + API)
- Per-agent-execution: +$0.01-0.10 (LLM tokens + compute)
- Consulting delivery: +$5-15k per client engagement

### Pricing Model (W8)
- **Consulting-first spine:** $50k-500k per engagement (3-12 month term) depending on org size + scope
- **Software margin mix:** Post-deployment SaaS (per-user or per-org pricing, 20-40% margin)
- **Equity default:** High-impact transformative engagements get equity + cash

---

## VII. Success Metrics

### Product Metrics
- **Thought-to-output compression:** Baseline 24 hours (status quo) -> 4 hours (V1) -> 30min (mature)
- **Engagement:** Daily active users, session depth, repeat rate
- **OKR alignment:** % of tasks scoring above 80% alignment to stated objectives
- **Autonomy graduation:** % of agent decisions > 90% aligned to user preference

### Business Metrics
- **Pilot outcomes:** 30/60/90 success thresholds (set in W8.3)
- **NPS:** Design partner satisfaction (target >50)
- **Expansion:** 2nd/3rd design partner signed (domino effect)
- **Achievement ledger:** Signed pilot = raise trigger (W10.2)

### Operational Metrics
- **API availability:** 99.5% uptime SLA
- **Latency:** p99 < 2s for API calls, <5s for agent execution
- **Error rate:** <0.1% of requests; <5% of agent tasks
- **Cost per customer:** <10% of consulting revenue

---

## VIII. Risk Mitigation

### Technical Risks

| Risk | Mitigation |
|------|-----------|
| Multi-tenant data isolation failure | RLS + schema separation + quarterly pen test |
| Agent cost explosion | Token budgeting per org + usage monitoring + auto-pause |
| Meeting transcription errors | Otter + Recall redundancy + human review on critical items |
| LLM model outdating | Multi-model abstraction (LiteLLM) + cached results |

### Business Risks

| Risk | Mitigation |
|------|-----------|
| Design partner churn | Weekly check-ins + early outcome wins + feedback loop |
| Moat erosion (frontier labs ship OS) | Pivot to "trusted companion" positioning + bundle with consulting |
| Hiring bottleneck (single-operator estate) | Contribution-earns-equity for Nick/Carter + structured delegation |
| Cold institutional capital (unfamiliar with model) | Raise from known investors only; syndicate after first pilot |

### Compliance Risks

| Risk | Mitigation |
|------|-----------|
| GDPR/CCPA violations | Data map + retention policy + consent flows (W9) |
| Security breach | Incident response playbook + cyber insurance + 24h notification |
| Audit failure (enterprise deal) | SOC2-aligned controls now + formal audit Month 9 |

---

## IX. Guardrails & Non-Negotiables

1. **No em dashes.** (Universal rule; explicit recipient preference.)
2. **Honest math.** Every statistic carries MEASURED/SURVEY/VENDOR lineage; no overclaim.
3. **Human gates on high-impact decisions.** Money, irreversible actions, external commitments always require approval.
4. **Graduation rule is law.** Agents earn autonomy via 90%+ alignment over 20+ reps per decision class; don't shorten this.
5. **Compensation is decoupled from gamification.** Points/streaks/leagues are *motivational*, never tied to pay.
6. **Product is unnamed until Jarred decides.** No permanent name before MVP.
7. **Founder control preserved.** Equity for Nick/Carter via contribution milestones, not co-founder splits.
8. **Upexi completely separate.** This initiative has nothing to do with Upexi the company; investor duality disclosed in writing.

---

## X. Next Steps (First 7 Days)

1. **W0.5:** Verify no three-founders framing survives
2. **W2.3-2.5:** Entity formation + IP assignment + founder operating model (counsel-gated)
3. **W3.2:** Begin exec-gui answer-relay spike (live read-only demo for 7/17)
4. **W1.7:** Counsel securities pass on full concept doc + deck
5. **W10.3:** Known-investor relationship map (CRM pointers only)

---

**This document is the foundational build strategy. Every team member should have internalized this before starting work on their assigned pillar. Questions or conflicts with this strategy should be raised with Jarred immediately (founder veto applies).**

