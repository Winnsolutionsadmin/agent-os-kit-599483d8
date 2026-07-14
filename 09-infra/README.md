# 09-infra: End-to-End Infrastructure + Dev Strategy

The authoritative build strategy for the UNNAMED product (Agent OS is a descriptor). Founder: Jarred Winn. Mirrored on the ClickUp board under the W-INFRA anchor (86ey7m369, list 901819360023).

## The five authoritative artifacts (2026-07-08, corpus-grounded)

Read in this order; where anything in this folder conflicts, THESE govern:

1. **architecture-overview.md** - system map: front door (read-only relay first, per W3 founder decision), capture pipeline, OKR engine, achievement/gamification layer, attribution (future wedge, zero build), fleet orchestration, PM-tool adapter, multi-model hedge, tenant substrate. Consolidate-vs-rebuild verdicts per pillar.
2. **product-law-enforcement.md** - how the gates are IMPLEMENTED: gate service, decision-class registry (with NEVER-GRADUATE classes), graduation ledger (90%/20+ reps; edit = disagreement, conservative read pending founder confirm), immutable audit log, kill criterion, fail-open-to-the-human surfacing, zero-ungated as a computed invariant.
3. **data-governance-architecture.md** - W9 working draft: data map, pilot vs V1 tenant isolation, consent/retention/breach/surveillance posture, SOC2-aligned controls now with the formal audit triggered by the first enterprise deal.
4. **dev-strategy.md** - repo strategy (/newproject-trio at first product commit, name deferred), three-rung environments, the wiggum-loop dev model, CI/CD, testing including the gate-invariant suite, instrumentation plumbing, security baseline, single-operator capacity honesty.
5. **build-sequence.md** - dependency-ordered plan on the pilot timeline (spike pre-7/15; days 1-30 capture + ONE gated workflow; 31-90 gamification; months 2-6 to V1) with per-phase definition of done and full backlog traceability.

## Inherited drafts (reference inputs, NOT authoritative)

**INFRA-STRATEGY.md** and **API-SPECIFICATION.md** were authored earlier on this branch as a first pass. Kept as useful raw material (pillar buildout lists, API resource sketches), but read them with this audit note:

- Their cost table (section VI) and several stack picks carry NO lineage tags; treat every number there as [unverified].
- Stale/incorrect specifics: "Claude 3.5 Sonnet" and "Llama 2 70B" as model choices, Pinecone/LangChain/Salesforce boilerplate not decided anywhere in the corpus, references to per-pillar "teams" that do not exist (single-operator estate, counsel blind spot 3).
- "Multi-tenant from day one" (its non-negotiable 1) is superseded by the decided pilot posture: segregated single-tenant pilot first, multi-tenant at V1 (data-governance-architecture.md section 2).
- Their phase plan predates build-sequence.md; build-sequence.md governs.

Detailed endpoint specs, when the product repo is born, should grow from API-SPECIFICATION.md's resource sketches but be re-grounded against the five artifacts above.

## Standing rules for anything authored here

- No em dashes. Product UNNAMED. No Upexi, no Mima. Recurro only as Carter's framework.
- Honest math: MEASURED / SURVEY / VENDOR / [unverified] lineage on every number.
- Product law is an architectural invariant (counsel: "don't touch it"). Founder-level questions go in a "Needs founder" section, never decided in-file.
- Readiness scores never in anything deck-bound.
