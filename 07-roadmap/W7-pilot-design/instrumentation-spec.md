# Pilot instrumentation spec: what gets measured from day 1 (task 7.3)

**Workstream:** W7 pilot design + instrumentation | **Task:** 7.3 | **Authored:** 2026-07-08
**Status:** done, research-loop output. This spec exists so the 30/60/90 thresholds (`07-roadmap/W8-unit-economics/buyer-roi-model.md`, all threshold numbers [unverified] candidates) and the achievement ledger (W10 task 10.2) have data from day 1. Event names are working identifiers, not product naming (the product is UNNAMED).
**Inputs:** `buyer-roi-model.md` (B1-B5 baselines, 30/60/90 gates), `days-1-30-plan.md` (7.1), `days-31-90-plan.md` (7.2), `01-overview/product-concept-overview-2026-07-08.md` sections 3 and 5, W9 backlog (`07-roadmap/W9-data-governance/tasks.md`), W10 backlog.
**Lineage legend:** MEASURED / SURVEY / VENDOR / [unverified], as defined in the ICP doc.

**Instrumentation laws:**

1. **One event stream, three consumers:** the 30/60/90 threshold evaluation (W8), the achievement ledger (W10), and, from day 31, the gamification scoring engine (W4/Nick). No consumer gets a private, differently-counted stream; honest math requires one source of truth.
2. **Silence must look like breakage** (must-have 22): a designated meeting that produces no capture event is an incident, not a gap in the data.
3. **Measure output and value, not hours or activity** (must-have 14): activity events exist to compute loop-deletion outcomes (hours recovered, debt cleared, attention cost), never to rank busyness.
4. **The zero-ungated attestation is computed, not asserted:** it falls out of the event stream (section 2, E10) or it does not exist.

---

## 1. What each pilot gate needs (traceability, from `buyer-roi-model.md` section 3)

| Gate requirement | Metric | Events that feed it |
|------------------|--------|---------------------|
| Day 30: capture coverage 90%+ [unverified candidate] | designated meetings captured / designated meetings held | E1, E2, E3 |
| Day 30: 15+ gated executions, ZERO ungated (zero is hard) | execution and gate-decision counts | E8, E9, E10 |
| Day 30: baseline signed | baseline artifacts on file | E20-E23 |
| Day 30: B2 trending down | open follow-up debt over time | E5, E6, E7 |
| Day 60: adoption 60%+ weekly active [unverified candidate] | cohort weekly-active ratio | E15, E16 |
| Day 60: B1 at 3+ hours/week recovered [unverified as client expectation; band MEASURED n=1] | recovered-hours vs B1 baseline | E4, E20, weekly attestation E24 |
| Day 60: B2 down 50%+ [unverified candidate] | debt vs day-0 count | E5-E7 vs E21 |
| Day 60/90: graduation progress / status | agreement rate per decision class over reps | E9 (agreement fields) |
| Day 90: B1 sustained 3-6 hours/week across 4+ weeks | weekly series | E4, E24 |
| Day 90: B3 client-MEASURED attention cost | touches + approvals + attention seconds per delegated-work day | E11, E12 |
| Day 90: conversion, reference, domino-2 | business events | E31-E33 |

Until day 90, B3 remains labeled everywhere as the built demo scenario (14 actions, 3 approvals, 41 seconds), NOT a client result.

## 2. Event list

Working event identifiers. Payload fields listed are the minimum for the gates; W9 governs what may be stored at all (section 5).

**Capture events (day 1):**
- **E1 `meeting.designated`** - a meeting enters the designated capture surface (scope decision by the executive; carve-outs per ICP disqualifier 6 are recorded as scope, not as content).
- **E2 `meeting.captured`** - capture succeeded; fields: meeting ref, duration, artifact counts.
- **E3 `meeting.capture_missed`** - a designated meeting produced no capture (incident-grade, law 2); fields: meeting ref, reason.
- **E4 `artifact.produced`** - a decision/action/commitment artifact created from capture; fields: type, source meeting, executive touch time.

**Follow-up / commitment events (day 1):**
- **E5 `commitment.opened`** - a commitment (own or others') enters tracking.
- **E6 `commitment.cleared`** - closed with disposition (done, delegated, dropped-deliberately).
- **E7 `commitment.overdue`** - crossed its due state (B2 is the count of open E7 states at a point in time).

**Gated-workflow events (day 1, on THE one workflow):**
- **E8 `workflow.execution.proposed`** - the agent proposes an execution; fields: decision class, proposal ref.
- **E9 `workflow.gate.decided`** - the human gate resolved; fields: decision class, outcome (approve / edit / reject), agreement flag (approve without edit = agreement; edit or reject = disagreement), latency from E8. This event IS the graduation math: 90% agreement over 20+ reps per decision class computes from E9 alone.
- **E10 `workflow.ungated_attempt`** - any attempted money/irreversible/external action that did not pass a gate. Target count: ZERO, hard requirement. Sev-1: workflow pauses, incident recorded, executive informed (per 7.1 section 5). The day-30 zero-ungated attestation is "count(E10) = 0 over the phase," computed from the stream.
- **E11 `executive.touch`** - each executive interaction with the system; fields: surface, seconds of attention (B3 numerator components: touches + approvals + time).
- **E12 `delegated_work.day_summary`** - daily rollup: agent work performed vs E11 totals (B3 denominator: per delegated-work day).
- **E13 `decision.latency_sample`** - request-to-decision elapsed time on the chosen workflow (B4); baseline comes from the pre-pilot timestamp audit (E23).
- **E14 `meeting.output_conversion_sample`** - weekly: meetings held vs meetings producing captured decision/action artifacts (B5, secondary).

**Gamification events (day 31+, only after the day-30 evidence gate; consumed by Nick's scoring per the W4 handshake H3):**
- **E15 `cohort.optin` / `cohort.optout`** - individual opt-in/out (opt-out stops scoring forward; retention of past scoring data per W9 task 9.3 posture).
- **E16 `cohort.weekly_active`** - weekly-active flag per opted-in member (adoption ratio).
- **E17 `score.event`** - a scoring event fired (rarity x impact semantics are Nick's, W4; the underlying fact events are E2/E4/E6/E9).
- **E18 `antiabuse.flag`** - cap hit, outlier detected, consistency-gate trip; fields: rule, member (reviewed weekly; "analyze the ones that hit the cap").

**Baseline + gate + business events:**
- **E20 `baseline.b1_signed`** - 2-week executive time audit complete and signed (hours/week on capturable loops: meeting notes, follow-up chasing, status assembly, reporting prep).
- **E21 `baseline.b2_signed`** - day-0 follow-up-debt count signed.
- **E22 `baseline.dollarization_agreed`** - buyer's own rate recorded, or explicit decline (then hours stay raw; never an asserted market rate).
- **E23 `baseline.b4_audit_complete`** - 90-day timestamp audit of the chosen workflow (runs after week-1 selection).
- **E24 `weekly.attestation`** - weekly check-in held; B1/B2 readings reviewed with the executive; kill-criterion glance.
- **E25 `workflow.selected`** - the week-1 rubric decision (workflow chosen, scores, executive's stated reason). Rubric scores are internal; never partner-slide material.
- **E30 `gate.cleared`** - day-30 / day-60 / day-90 gate evaluated; fields: gate, pass/fail per criterion, evidence refs.
- **E31 `pilot.signed`** - the signed design-partner pilot. THE raise trigger (founder-defined, W10 task 10.2). Recorded at signature, before day 1.
- **E32 `conversion.decided`** - post-pilot retainer signed or declined, with reasons.
- **E33 `expansion.conversation_opened`** - domino-2 sponsorship conversation opened (yes/no), reference permission granted (yes/no).
- **E34 `kill_criterion.evaluated`** - the written kill criterion formally evaluated (day-30 checkpoint and any triggered evaluation); fields: outcome, reasons.

## 3. Capture points (where events originate)

| Capture point | Estate pattern it generalizes | Events |
|---------------|-------------------------------|--------|
| Meeting capture pipeline | fieldy-clawdia + recall-notetaker stack (MEASURED, Tier A; sanctioned capture only, must-have 7) | E1-E4, E14 |
| Commitment/CRM store | CRM relationship stack, follow-up tracking (MEASURED, Tier A) | E5-E7 |
| Approvals / decision-card surface | bar Approvals panel, command-center cards (Tier A/B) | E8-E11, E25 |
| Task backbone adapter | ClickUp-first, PM-tool-agnostic adapter interface per counsel revision 7 | E4 landings, E6, E13 |
| Weekly check-in log | operator-maintained, countersigned at the check-in | E24, E30, E34 |
| Scoring engine (day 31+) | mini achievement engine generalized per Nick's W4 mechanics | E15-E18 |
| Contract/business record | operator-maintained | E20-E23, E31-E33 |

Instrumentation is stood up in week 1 alongside capture go-live (7.1 section 5); E31 and E20-E22 precede day 1 by definition.

## 4. Baseline-signing procedure (pre-day-1; contract-mandated per ICP disqualifier 4)

1. **Name the business owner.** A named owner (the CEO or their delegate with authority; SURVEY: named metric + named C-1+ sponsor are two of the four factors explaining 71% of payback-speed variance, attributed to Bain, secondhand) countersigns everything below.
2. **B1 time audit (2 weeks, pre-pilot):** the executive logs hours/week on the four capturable-loop categories. Instrument is a daily 2-minute self-report plus calendar cross-check; both parts retained as the audit trail. Output signed as E20.
3. **B2 debt count (day 0):** CRM/task export plus meeting-note sweep produces the open-commitment and overdue counts. Output signed as E21.
4. **Dollarization rule settled:** the buyer states their own rate for their time, or declines; recorded as E22. Honest-math law: hours are never dollarized at an asserted market rate.
5. **Kill criterion written:** one falsifiable sentence, agreed and signed (evaluated at day 30 and on trigger; E34).
6. **Capture scope designated:** the executive designates the meeting surface; disclosure-sensitive scope carved out per ICP disqualifier 6 until W9 lands. The scope document is part of the signed baseline.
7. **B4 audit (week 1, post-selection):** timestamp audit of the chosen workflow's last 90 days; signed as E23.

The signed baseline package (items 1-6) is itself a ledger artifact (see section 6) and a contract exhibit (task 7.4).

## 5. Consent posture (pointer to W9, a pre-pilot dependency)

- **W9 (data governance + tenant isolation) is a pre-pilot dependency for anything in this spec that touches partner-employee data.** Specifically: E1-E4 capture involving employees other than the executive, E15-E18 cohort scoring data (named in W9 task 9.3 as the sensitive class), and any retention of speaker-attributed content. W9 tasks 9.1 (data map), 9.2 (tenant isolation posture), and 9.3 (consent, retention, breach response, surveillance-risk posture; founder review) must have at least their pilot-phase posture answered before day 1 of capture beyond the executive's own desk.
- Until the W9 posture lands: instrumentation runs executive-only where necessary; capture is sanctioned and disclosed to all participants (must-have 7, the Winn.ai eviction lesson); disclosure-sensitive scope stays carved out (ICP disqualifier 6); no employee-level scoring data is collected before individual opt-in (E15) under a W9-approved consent text.
- Surveillance-risk framing is a values statement, not just engineering (W9 human gate): the pilot measures loop deletion and rewards, not people. Comp-decoupling (7.2 section 4) is part of that same posture.
- Tenant isolation: pilot-phase segregation model is W9 task 9.2's call; this spec only requires that partner event data is segregated from the reference-implementation estate and from any other account from day 1 [posture, not yet a spec; W9 owns it].

## 6. Which events write achievement-ledger entries (W10 handshake)

The raise trigger is the SIGNED design-partner pilot (founder-defined, W10 task 10.2). Everything else is supporting evidence a known investor can verify by talking to the design partner. Ledger-writing events, in sequence:

| Ledger entry | Source events | Trigger status |
|--------------|--------------|----------------|
| Signed pilot: named CEO owner, written baseline, kill criterion | E31 (+ E20-E22 refs) | **THE raise trigger** |
| Day-30 gate cleared: capture coverage %, gated-execution count, zero-ungated attestation, baseline artifact | E30(day30), E2/E1 ratio, E9 count, count(E10)=0, E20-E21 | supporting |
| Day-60 gate cleared: adoption %, hours recovered vs baseline, follow-up-debt delta, decision-class rep counts | E30(day60), E16, E4/E24 series, E5-E7 delta, E9 rollup | supporting |
| Day-90 gate cleared: sustained-hours evidence, debt end state, B3 client-measured, graduation status per class | E30(day90), E24 series, E7 state, E11/E12, E9 rollup | supporting |
| Conversion signed (or not, with reasons); reference permission | E32, E33 | supporting |
| Domino-2 conversation opened | E33 | supporting |
| Kill criterion outcome (including a clean stop; an honest stop is ledger-worthy) | E34 | supporting |

Non-ledger events (E11-E14, E17-E18, E25, raw E1-E10) stay in the pilot record as evidence backing, not as entries. The ledger schema itself is W10 task 10.2 (schema authoring open); this table is the W7-side input to it. Nothing in the ledger carries a readiness score or an internal band, and no ledger entry is deck material without its lineage tag.

## 7. Open items needing Jarred or a dependency

1. W9 pilot-phase posture (9.1-9.3) is the binding pre-pilot dependency; 9.3 carries a founder-review gate. Without it, capture beyond the executive's own desk and all cohort scoring stay off.
2. E15 opt-out data-retention behavior needs the W9 task 9.3 answer.
3. Whether E9 "edit" outcomes count as full disagreement for graduation math or as a weighted partial [design decision; this spec proposes edit = disagreement, the conservative read; founder confirmation].
4. Threshold numbers throughout remain [unverified] candidates inherited from 8.3 until the design partner signs the baseline.
5. The B3 demo figure (14 actions, 3 approvals, 41 seconds) appears in no partner-facing instrumentation output as a promise; confirm Jarred wants it even in the talk-track (8.3 open item 3).
