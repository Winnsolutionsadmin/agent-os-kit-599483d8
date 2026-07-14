# Achievement ledger

One file per entry, `YYYY-MM-DD-<slug>.md`, chronological by filename. Schema and rules: `../achievement-ledger-schema.md`.

The rules in brief:

- Two classes: `signed-commitment` (the trigger class; the first CONFIRMED `pilot.signed` entry IS the raise trigger, founder-defined 2026-07-08) and `supporting-evidence` (threshold clears, domino engagements, hardened artifacts; never a trigger).
- Every entry carries all seven fields: date, type, claim, lineage, proof, visibility, status. No proof pointer, no entry.
- Any loop can propose (status PROPOSED). Only the founder confirms, and only the founder sets `investor-visible: yes`.
- CONFIRMED entries are corrected by follow-up entries, never silent edits. PROPOSED entries may be edited until confirmed.
- Nothing PROPOSED and nothing `investor-visible: no` leaves this repo. Investor views render as stylized HTML/PDF; raw files never forward.
- Honest math throughout: lineage tags mandatory, smaller sourced numbers, no readiness scores, no raw multipliers without methodology, no projections. A pass is recorded as a pass.
