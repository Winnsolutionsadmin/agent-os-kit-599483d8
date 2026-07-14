# Roadmap map: from concept to reality (working scaffold, born 2026-07-08)

> Founder: Jarred Winn. Vision is his; originating members (Nick Metzler, Carter Razink) earn equity through contribution. Funding arrives on achievement + faith from investors Jarred already knows. Positioning: the trusted companion that brings companies through the AI transition and gives them the head start. Dominos: C-levels (chief of staff / organizer) -> engineers (revamp / overhaul) -> all else follows demand. This file is the map of HOW we execute: workstreams, branches, worktrees, tasks, and wiggum loops.

## Execution model: wiggum loops

Every workstream runs the same loop shape:
1. **Backlog file** in its folder (`tasks.md`) + mirrored rows on the ClickUp list (901819360023).
2. **Loop prompt**: a self-contained iteration prompt; an agent (or /loop-paced session) picks the top unblocked task, does it, commits the ARTIFACT (never a summary), updates the backlog, repeats until the backlog runs dry or a human gate is hit.
3. **Done-criteria** written before the loop starts; human gates on anything external, irreversible, or money.
4. **Worktree per workstream** via OmnaraBranch (visible in the app, steerable from the phone). Branch naming: `ws/<key>-<slug>`. One executor per branch; artifacts + commits cited on completion.
5. Loops that stall or go silent get liveness pulses; silence is treated as breakage.

## Workstreams (initial cut; the mapping session refines this WITH Jarred)

| Key | Workstream | Deliverable | Anchor date | Loop-able? |
|-----|-----------|-------------|-------------|------------|
| W0 | Foundation hygiene | grasp-verification patches applied; corrections everywhere | now | yes (patch loop) |
| W1 | Concept doc + deck | the 7/15 concept doc + early deck with branch scenarios, authored FROM this repo | 7/15 | partially (draft loop + founder review gates) |
| W2 | Entity + equity framework | formation, IP assignment, contribution-earns-equity design for originating members (founder control preserved) | this week | no (counsel + founder) |
| W3 | Front-door build | exec-gui answer-relay spike -> one live front-door demo -> V1 surface (graduates to its own code repo at first commit of product code) | spike pre-7/15 | yes |
| W4 | Gamification mechanics | Nick's mechanics spec ingested -> anti-abuse design doc -> scoring model (decoupled from comp) | 7/31 | yes after Nick input |
| W5 | OKR engine productization | generalize the-sage pattern: org OKR tree -> weighted agent subtasks -> outcome scoring | month 1-2 | yes |
| W6 | Case study hardening | Carter methodology memo -> defensible achievement artifact (output-parity fallback) | 7/15 | no (Carter input gate) |
| W7 | Pilot design + instrumentation | 90-day design-partner pilot plan: days 1-30 capture + one gated workflow, 31-90 gamification | pre-pitch | yes |
| W8 | Unit economics + ICP | pricing, buyer ROI model, ICP definition (counsel blind spot 1) | month 1 | yes (research loop) |
| W9 | Data governance | tenant isolation, consent/retention, security posture (counsel blind spot 2) | month 1-2 | yes (research loop) |
| W10 | Trusted-companion narrative | positioning language, achievement ledger for known investors, relationship map | rolling | yes |

## Dependency spine (start to finish)

1. **Now -> 7/11:** W0 patches + W2 formation start + shared 3-way doc (Jarred authors; contribution-equity framing).
2. **7/11 -> 7/15:** W1 concept doc + deck (consumes W6 case study + W3 spike if landed); W7 pilot plan drafted into the deck's branch scenarios.
3. **7/17-18:** investor conversation (achievement + faith framing; design-partner structure).
4. **Days 1-30 post-commit:** W7 pilot phase 1 (capture + one gated workflow); W3 front-door hardening in parallel.
5. **Days 31-90:** gamification enters pilot (W4 + W5); achievement ledger accumulates (W10).
6. **Month 2-6:** productization loops (W3/W4/W5 converge into the V1 surface); W8/W9 close; second/third design partners via the domino ladder.
7. **~Month 6:** achievement-triggered raise from known investors; scale team via contribution-earned equity.

## Branch / worktree / repo conventions

- THIS repo (agent-os-foundation): documents, research, roadmap, backlogs. Branches: `ws/<key>-<slug>`, merged to main when the artifact lands.
- Product CODE gets its own repo at the first real commit (candidate name deferred; product is unnamed). The trio (repo + ClickUp + Drive) is created via /newproject-trio on that day.
- Omnara worktrees for every working session (OmnaraBranch skill; never bare `git worktree add`).
- ClickUp list 901819360023 is the cross-agent board; every workstream task mirrored there on state change.

## Workstream folders (elaborated 2026-07-08, roadmap-mapping session)

Every workstream now has `07-roadmap/W<n>-<slug>/tasks.md` (seeded backlog with per-row gates). W0/W1/W3 carry bespoke `loop.md`; W4-W10 run `LOOP-TEMPLATE.md`. Backlogs are mirrored to ClickUp list 901819360023 at workstream level; task rows sync on state change.

## Open mapping questions

RESOLVED (mapping session, 2026-07-08):
- Partner deliverables land in `08-partner-inputs/` (verbatim, one file per deliverable, synthesis happens in workstream folders). See its README.
- Cheapest first loops: W0 (partial: grasp report still pending) and W8/W7 (both feed the 7/15 deck). Backlogs are seeded and launch-ready.
- W2 mechanism: FOUNDER PICKED Option C hybrid (small time-vested base + milestone kickers; fallback Option A if counsel bandwidth is short). Details in `W2-entity-equity/contribution-equity-options.md`.
- W3 spike scope: FOUNDER DECIDED live READ-ONLY estate readout (answer-relay wired to one real surface; no live action paths in the 7/17-18 room). W3 loop is unblocked.

- W10 achievement definition: FOUNDER DEFINED (2026-07-08): the raise trigger is a SIGNED DESIGN-PARTNER PILOT; metrics, second-domino pull, and the hardened case study are supporting ledger evidence, not the trigger.

ALL MAPPING QUESTIONS CLOSED (2026-07-08). The map is complete start to finish; execution proceeds per workstream backlogs.
