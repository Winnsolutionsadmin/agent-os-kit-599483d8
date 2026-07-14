# Achievement ledger schema (task 10.2, schema half)

**Workstream:** W10 narrative + ledger | **Task:** 10.2 | **Authored:** 2026-07-08
**Status:** schema DONE; the DEFINITION was closed by the founder before authoring. Ledger seeded at `ledger/`.
**Founder definition (closed, 2026-07-08):** the raise trigger is a SIGNED design-partner pilot. Pilot metrics, the second-domino pull, and the hardened case study are ledger-worthy supporting evidence but are NOT the trigger.
**Inputs:** `memory-bank/decisions/0003-founder-structure-funding-positioning.md`; `07-roadmap/W7-pilot-design/instrumentation-spec.md` section 6 (the W7-side handshake table); `07-roadmap/W7-pilot-design/deck-branch-scenarios.md` (per-branch ledger records); `positioning-language-bank.md` section (e).
**Purpose:** the funding model is achievement plus faith from investors Jarred already knows. The ledger is the achievement half made verifiable: a chronological, lineage-tagged record a known investor can walk through and check. It is not a marketing surface and it is not a metrics dashboard; it records events that already happened, with proof.

---

## 1. Entry types

Two classes. The class boundary is founder-defined and closed.

### 1.1 `signed-commitment` (the trigger class)

Events where a counterparty put a signature or money on paper.

- **`pilot.signed`**: a design-partner pilot signed (named CEO owner, written baseline, kill criterion). Maps to instrumentation event E31. **The first entry of this type IS the raise trigger.** Subsequent signed pilots are also this type; each strengthens the ledger but the trigger fires once.
- **`check.closed`**: a strategic check closed on its own paper (the faith component, recorded distinctly per branch scenario B; never contingent on and never substituting for the pilot entry).
- **`conversion.signed`**: post-pilot retainer or expansion signed. Maps to E32.

### 1.2 `supporting-evidence` (never a trigger)

Everything else worth showing a known investor. Three sub-classes:

- **`threshold-clear`**: a 30/60/90 gate evaluated, per instrumentation-spec.md section 6. Day-30 (capture coverage, gated-execution count, the computed zero-ungated attestation, signed baseline), day-60 (adoption, hours recovered vs B1, debt delta, graduation reps), day-90 (sustained hours, B3 client-MEASURED, graduation status). Source events E30 plus the backing rollups. A kill-criterion outcome (E34) is also this sub-class: an honest stop is ledger-worthy.
- **`domino-engagement`**: a domino-2 sponsorship conversation opened, a reference permission granted, a next-domino pull recorded (E33). Also covers a meeting held with a branch outcome and stated reasons (branch C: a pass is recorded as a pass, never reframed as interest).
- **`hardened-artifact`**: an artifact reaching evidence grade. Examples: Carter's 16x methodology memo landing (until then the case study stays out of decks), the counsel securities pass completing, entity formation and IP assignment executed, the concept doc and deck shipping in final render, this repo reaching a mapped and committed state.

## 2. Per-entry fields

Every entry file carries all seven. No field is optional.

| Field | Content | Rules |
|---|---|---|
| `date` | YYYY-MM-DD the event occurred (not when recorded) | If recorded later, note the recording date too |
| `type` | `signed-commitment` or `supporting-evidence`, plus the sub-type from section 1 | Trigger status is derivable from type; never asserted separately |
| `claim` | One sentence stating what happened, written so a skeptic can check it | Honest math: the smaller sourced number; loop-deletion framing over raw multipliers; no readiness scores, no internal bands, ever |
| `lineage` | MEASURED / SURVEY / VENDOR / [unverified], per the repo-wide legend | An [unverified] entry may exist but is never investor-visible |
| `proof` | Pointer a reader can follow: commit sha, contract reference, signed baseline artifact, dashboard or event-stream query (e.g. count(E10) = 0 over the phase), source URL | No proof pointer, no entry. "Trust me" is not a proof type |
| `visibility` | `investor-visible: yes/no` | Only the founder flips this to yes (section 4) |
| `status` | `PROPOSED` or `CONFIRMED` | PROPOSED entries carry `[proposed, awaiting founder confirm]` in the title line |

## 3. Where entries live

- **This repo**, at `07-roadmap/W10-narrative-ledger/ledger/`, one markdown file per entry.
- **Filename convention:** `YYYY-MM-DD-<slug>.md`, e.g. `2026-07-08-foundation-repo-complete.md`. Chronological sort is the read order.
- `ledger/README.md` states the rules of the directory and is not itself an entry.
- Entries are append-only in spirit: a wrong entry is corrected by a follow-up entry that references it, not by silent edits, once it has been CONFIRMED. PROPOSED entries may be edited freely until confirmed.

## 4. Who writes

- **Any loop can propose.** Any workstream loop (W1-W10), any session, any agent working this repo may add a PROPOSED entry when its work produces a ledger-worthy event. Instrumentation-spec.md section 6 defines which pilot events auto-qualify for proposal.
- **The founder confirms.** Only Jarred moves an entry from PROPOSED to CONFIRMED, and only Jarred sets `investor-visible: yes`. Signed-commitment entries additionally require the paper to exist before confirmation (the proof pointer must resolve to a contract reference, not an intention).
- Nothing PROPOSED, and nothing with `investor-visible: no`, ever leaves this repo or appears in any external artifact.

## 5. The read path: how a raise conversation consumes the ledger

1. **Check the trigger first.** Is there a CONFIRMED `signed-commitment / pilot.signed` entry? If no: there is no raise conversation, only relationship maintenance (branch C posture: evidence milestones shared when they exist). If yes: the trigger has fired and the conversation is live.
2. **Assemble the investor view.** Filter to CONFIRMED entries with `investor-visible: yes`, sorted by date. That chronological list IS the achievement narrative; it needs no embellishment because every line carries a claim, a lineage tag, and a proof pointer.
3. **Render, never forward.** The investor view is rendered into a stylized HTML/PDF evidence package (client-facing artifact law). Raw ledger files never leave the repo. Disclosure scope for anything naming the design partner follows the partner-approved scope in the pilot terms (terms skeleton section 8).
4. **The conversation walks the entries.** Each supporting-evidence entry is offered as something the investor can verify independently: talk to the design partner, click the source, read the signed baseline. Verifiability is the point; the funding model is faith attaching to checkable achievement, not narrative.
5. **The ask stays banked.** The language of the conversation comes from `positioning-language-bank.md` section (e). The evidence-backed syndicate raise targets ~month 6; before that, the only asks are the pilot and the smaller strategic check.

## 6. What never enters the ledger

- Readiness scores, internal bands, rubric numbers (hard law: internal tools only).
- Raw multipliers without lineage (the 16x figure enters only inside a `hardened-artifact` entry for Carter's methodology memo).
- Projections, intentions, or pipeline ("we expect to sign" is not an event).
- Anything premised on Upexi or Mima, and any product name (the product is UNNAMED).
- Personal data about investors (W10 task 10.3 keeps relationship data as pointers to CRM/Drive, never dumped here).

## Open items needing Jarred

1. Confirm the seeded 2026-07-08 entry (`ledger/2026-07-08-foundation-repo-complete.md`, PROPOSED).
2. Confirm the `check.closed` entry type sits in the signed-commitment class as authored (branch scenario B implies it; the founder definition named only the pilot as trigger, and this schema keeps it non-trigger accordingly).
