# Data Governance Architecture (09-infra artifact 3 of 5, W9 alignment)

**Authored:** 2026-07-08, infra-clickup session
**Alignment:** this is the infrastructure-side working draft for W9 (counsel blind spot 2). W9 tasks 9.1-9.5 remain the workstream of record; their outputs supersede this draft where they differ. W9 task 9.3 (consent/retention/surveillance posture) carries a FOUNDER review gate because surveillance posture is a values statement, not just engineering.
**Sources:** W9 backlog, W7 instrumentation-spec section 5, 04-competitive/risk-security-compliance.md (Upexi-premised passages invalid as premised; compliance evidence used here is Upexi-independent), 03-execution/enterprise-deployment.md, counsel verdict 6.
**Lineage legend:** MEASURED / SURVEY / VENDOR / [unverified].

---

## 1. Data map (W9.1 working draft)

| Data class | What it is | Where it lives | Who can see it | Sensitivity |
|---|---|---|---|---|
| Meeting capture | designated-meeting transcripts, decision/action artifacts (E1-E4) | capture store (partner-segregated), embeddings index | executive + explicitly consented participants; operator under support policy | HIGH; privilege + wiretap exposure |
| Commitment/CRM | commitments, follow-up debt, contact records (E5-E7) | commitment store; partner PM tool via adapter | partner workspace members per their own tool ACLs | MEDIUM |
| OKR data | org tree, KR states, weighted subtask mappings | OKR store | partner org per role | MEDIUM; strategy-revealing |
| Scoring data | per-person gamification events, scores, anti-abuse flags (E15-E18) | scoring store, opt-in members only | THE SENSITIVE CLASS (W9.3): the individual, org admins per consented policy; never comp systems | HIGHEST |
| Gate/audit records | E8-E10, E34, graduation ledger | immutable audit log | operator + partner security on request | HIGH; evidentiary |
| Baselines/business | signed baselines, gate evaluations, contract events (E20-E34) | pilot record | founder + partner business owner | MEDIUM |
| Model traffic | prompts/outputs to LLM providers | provider-side per DPA; ZDR where granted | nobody at rest under ZDR; note Covered-Models carve-out (no ZDR, mandatory 30-day retention, VENDOR terms) | HIGH |

Rule from the map: scoring data and meeting capture never share a store, a key, or an access role with each other (segregation is control 1 of the SOC2-aligned set).

## 2. Tenant isolation model: pilot vs V1 (W9.2 working draft)

**Pilot phase (one design partner):**
- Dedicated single-tenant deployment: partner data in its own database instance and its own encryption keys, physically segregated from the reference-implementation estate and from any other account from day 1 (instrumentation-spec section 5 requirement).
- Estate-hosted is acceptable for the pilot ONLY with this segregation plus disclosed hosting posture in the pilot terms (W7.4). No partner data on shared estate machines' general stores.
- Rationale: at n=1, instance-per-tenant is cheaper to reason about and to attest than RLS, and a design partner's security team can audit it in one meeting.

**V1 (multi-tenant):**
- Postgres schema-per-tenant plus row-level security enforcing org_id on every query (defense in depth: RLS is the backstop, schema separation the primary boundary).
- Per-tenant encryption keys via cloud KMS; per-tenant API quotas and token budgets; tenant-aware structured logging on every request.
- Cross-tenant leak tests in CI (dev-strategy.md section 6): a synthetic two-tenant fixture where any query returning the other tenant's rows fails the build.
- Upgrade path to instance-per-tenant for regulated buyers who require it, priced into that contract (enterprise-deployment.md option 5 logic).

## 3. Consent, retention, breach, surveillance posture (W9.3 working draft; FOUNDER gate)

**Consent:**
- Sanctioned capture only (must-have 7, the Winn.ai eviction lesson: 16+ undisclosed notetakers forensically evicted from the estate's own accounts this week, MEASURED). No undisclosed bots ever.
- Executive designates the capture scope (E1); all participants receive disclosure; speaker attribution requires explicit all-party consent before it deploys in any multi-party meeting (active BIPA/wiretap class actions against the Otter/Fireflies feature class, VENDOR/press 2025-2026; first federal ruling pending).
- Employee-level scoring: individual opt-in (E15) under a W9-approved consent text before ANY collection; opt-out stops forward scoring; retention of past scoring data on opt-out is a W9.3 decision (proposed default: anonymize within 30 days, [unverified] as policy until founder review).
- Hard wall by policy before any regulated-client pilot: legal, board, and M&A meetings never enter capture (privilege exposure: 2026 Heppner holding that AI conversations are not privileged, VENDOR/press).

**Retention (proposed defaults, W9.3 to confirm):**
- Raw transcripts: 90 days then auto-delete unless explicitly archived by the partner.
- Derived artifacts (decisions, actions, commitments): life of the engagement plus contract-defined wind-down.
- Scoring events: engagement life; anonymized aggregates thereafter.
- Audit log: never deleted within the engagement; exported to the partner at wind-down.
- Provider-side: request ZDR in writing; route nothing sensitive to Covered Models where ZDR is unavailable.

**Breach response:**
- 24-hour internal notification, 72-hour partner notification commitment (GDPR-shaped even for US pilots; it is the posture a security team expects).
- Tenant-aware audit logging makes blast-radius determination a query, not an investigation.
- Incident playbook is a W9.4 deliverable; the E10 sev-1 machinery (product-law-enforcement.md section 6) doubles as the incident-recording spine.

**Surveillance posture (the values statement):**
- The product measures loop deletion and rewards, never people-watching: comp-decoupling at the code level, opt-in scoring, caps-and-outlier analysis directed at protecting people from the system rather than ranking them (W4 anti-abuse primitives).
- EU AI Act flag: OKR-weighted scoring plus gamification of workers reads literally as Annex III high-risk (worker monitoring/task allocation), enforceable August 2026 (VENDOR/press). Not a US-pilot blocker; becomes binding the moment any client has EU employee population. Design consequence now: the logging, human-oversight, and risk-management documentation the Act requires is the same artifact set the gate service and audit log already produce. Keep them export-ready.

## 4. SOC2-aligned controls now; formal audit on the first enterprise deal (counsel verdict 6)

**Now (the four counsel-named controls plus two):**
1. Data map: section 1, kept current per release (W9.1 owns it).
2. Access control: SSO + MFA on all infrastructure; RBAC in the application; scoring-store access is its own role.
3. Logging: all system and application access to the immutable log; tenant_id on every line.
4. Vendor review: quarterly assessment of every third party touching partner data (capture vendors, LLM providers via DPA + subprocessor list, PM tools, hosting). Attach Anthropic's current commercial DPA and subprocessor list to any client security exhibit rather than re-promising terms Anthropic sets (enterprise-deployment.md recommendation 6).
5. Encryption: at rest and TLS in transit, per-tenant keys per section 2.
6. Change management: branch protection, review gates, deploy gates (dev-strategy.md), because a security questionnaire asks.

**Formal audit:** SOC 2 Type II triggered by the first real enterprise deal. Realistic clock from a standing start: 9-15+ months and $30K-150K audit engagement / $90K-150K+ first-year total (SURVEY, 2025-2026 compliance-market sources cited in 04-competitive/risk-security-compliance.md). Never imply readiness before it exists; the pilot sells on relationship, demo, and this documented posture, not on certificates we do not hold.

**W9.5 standing rule:** the 83-99% SOC2-buyer-requirement stat is SURVEY-secondhand today and must be independently sourced before ANY deck use. Until then it appears in internal docs only, tagged.

## 5. Governance one-pager test

W9's done criterion is a governance one-pager that survives a design partner's security team's first meeting. This draft gives that one-pager its skeleton: data map table, pilot isolation model, consent posture, retention defaults, breach commitment, control set, audit trigger. The one-pager itself is a W9 artifact and gets founder review (9.3) before it is partner-facing.

## 6. Needs founder (routes through W9.3 review)

1. Retention defaults in section 3 (90-day transcripts, opt-out anonymization window).
2. Surveillance-posture language sign-off (it will be quoted back to us by partner security teams).
3. Whether pilot hosting is estate-hosted-segregated (proposed) or partner-cloud from day 1 if the partner offers it.
4. Scoring-data visibility for org admins: proposed default is aggregate-only without named-individual drill-down unless the individual consents; confirm.
