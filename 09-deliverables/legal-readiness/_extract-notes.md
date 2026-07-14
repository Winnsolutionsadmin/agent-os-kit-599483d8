# Legal-readiness extract notes — raw material for the author

**Compiled:** 2026-07-09 (extracted fresh; no prior `_extract-notes.md` existed for this lane).
**Method:** full read of `CLAUDE.md` (repo root), `05-counsel/counsel-deepdive-2026-07-09.md` (all addenda), `07-roadmap/W2-entity-equity/` (contribution-equity-options, shared-doc-skeleton, tasks), `07-roadmap/W9-data-governance/tasks.md`, `memory-bank/decisions/0003`, and the three Track-3 legal dossiers (`03-execution/venture-structure.md`, `gap-which-entity-*.md`, `gap-securities-*.md`). One timeboxed WebSearch for the current YC post-money SAFE form structure.

---

## GOVERNING CORRECTIONS (these override the Track-3 dossiers, which are all flagged PRE-Upexi / PRE-0003)

The three legal dossiers carry an explicit W0-hygiene caveat: they were written before decision 0003 and before the Upexi correction. Everything premised on Upexi, on a "$10-50M" ask, on a "three-way founding partnership", or on a fixed 55-65 / 20-25 / 10-15 split is INVALID AS PREMISED. The corrected frame that governs every document authored here:

1. **Jarred is THE founder.** Nick Metzler and Carter Razink are ORIGINATING MEMBERS who earn equity through contribution. Never "co-founder", never "three founders", never a fixed split. (`decisions/0003`, `CLAUDE.md` correction 5.)
2. **Equity mechanism is Option C hybrid** (founder-decided 2026-07-08): a small time-vested base grant per originating member (cliff included) plus milestone kickers tied to named deliverables. Fallback: Option A pure (milestone-vested only) if counsel bandwidth cannot carry two mechanisms. Percentages are set with counsel + Jarred only; none appear in any artifact. (`07-roadmap/W2-entity-equity/contribution-equity-options.md`.)
3. **Named deliverables that double as the vesting schedule:** Recurro framework doc (Carter, 7/10, vests on landed + usable by the engineering pillar); case study + methodology memo (Carter, 7/15, vests on surviving the honest-math audit); gamification mechanics definition (Nick, 7/31, vests on landed + anti-abuse coverage). (`07-roadmap/W2-entity-equity/shared-doc-skeleton-2026-07-11.md`.)
4. **The ask is two SEPARATE transactions** (codex B1): the pilot paper and the investment paper are distinct decisions with distinct evidence thresholds; a yes to one is never a yes to both; NO cross-contingencies anywhere. The canonical ask, verbatim: "A scoped 90-day design-partner pilot plus a smaller strategic check. The larger raise comes at roughly month 6, triggered by demonstrated achievement." Never "$10-50M".
5. **Recurro is Carter's own property** (his agentic-engineering framework, an input to the engineering pillar, not NewCo's product). If NewCo needs it, that is an explicit license-or-assignment DECISION for Carter + counsel, handled as a prior-inventions carve-out. (`CLAUDE.md` correction 2.)
6. **Mima is a separate venture** (personal AI + Trust Origin proof-of-humanity); excluded from the IP assignment entirely. (`CLAUDE.md` correction 4.)
7. **No Upexi anywhere.** The investor prospect (Alan) is engaged in a personal, separate capacity. Where an investor is also a client contact in a separate engagement, that is handled as ordinary written conflict-of-interest disclosure, nothing more. No UPXI math, no MNPI-premised-on-Upexi framing. (`CLAUDE.md` correction 3.)
8. **No em dashes. Every stat tagged** (MEASURED / SURVEY / VENDOR / CORPUS / ASSUMPTION). Built-vs-designed: nothing designed-but-unbuilt speaks in the present tense.

## TRANSFERABLE (survives the corrections) from the dossiers

- **IP mechanics** (`venture-structure.md`): present-tense "hereby assigns" language (not "agrees to assign"); real consideration (founder stock, not a gift); Section 83(b) election within 30 days of a stock grant tied to IP; background-IP vs foreground-IP schedule is the standard consulting-vs-product separation; prior-inventions carve-outs for every contributor; CA Labor Code 2870/2872 limits on invention-assignment reach (check existing client agreements for "improvements" clauses).
- **Vendors** (framework map only, counsel decides): Cooley GO free Delaware incorporation package; Clerky paid filing; Carta Launch free cap table under 25 stakeholders. Delaware C-corp is the diligence-standard shape.
- **Winn.solutions legal form is UNDOCUMENTED in the estate** — a real unresolved fact: cannot cleanly intercompany-license from an entity that may be a sole prop or DBA. Flag on doc 1.
- **Securities scaffolding** (`gap-securities-*.md`, stripped of Upexi): Reg D private placement + accredited-investor verification for the strategic check; Section 10(b)/Rule 10b-5 temporary-insider and misappropriation doctrines are the general backstop for any consultant given confidential access; written confidentiality is the standard cure. General federal law only; no Upexi facts carried.

## YC POST-MONEY SAFE (web-checked 2026-07-09, ycombinator.com/documents)

- Post-money SAFE is the standard since 2018 (replaced the pre-money SAFE). Current downloadable forms: **Postmoney Safe - Valuation Cap Only v1.1** (US) and **Postmoney Safe - MFN Only v1.2**; international variants for Canada / Cayman / Singapore.
- The **Valuation-Cap-AND-Discount** variant was removed from YC's site around August 2021 (archived on the Wayback Machine); the Safe User Guide still describes it. Discount Rate = 100 minus the discount percent.
- Post-money lets founder + investor compute dilution precisely at signing; usually only the valuation cap is negotiated; a SAFE has no maturity/interest. Source: `ycombinator.com/documents`, "Primer for post-money safe v1.1".

## CODEX / R-RULE GATES THAT BIND THIS LANE

- **R8** (pilot charter): one-page charter with named fields as blanks-to-fill; both branches rehearsed (investor IS the operating counterparty -> charter on the table; investor is NOT -> sponsorship + strategic check + a dated scoping session within 72h to name the counterparty).
- **B1** two-transaction separation; **B10** interim facts memorandum by 7/11 (founder/contributor/governance/IP facts; no implied executed agreements); **codex gate 4** every data-security control classified built-and-tested / internal-only / pilot-prerequisite / roadmap.
- W9.5: the 83-99% SOC2 buyer-requirement stat is UNSOURCED; do not use it anywhere until independently sourced.

## PER-DOC OWNERS / DEADLINES (for the banner blocks)

| Doc | Owner | Decision deadline |
|---|---|---|
| 1 Entity + IP checklist | Jarred + counsel | this week (before 7/17) |
| 2 Interim facts memorandum | Jarred (authors + signs), counsel blesses | 7/11 |
| 3 Contribution-equity term sheet outline | Jarred + counsel | this week, before milestone dates land |
| 4 Pilot success charter | Jarred | before 7/17 (BLOCKS the meeting) |
| 5 SAFE / instrument overview | Jarred + counsel | before terms are discussed (pre-7/17 readiness) |
| 6 Data-security one-pager | Jarred (+ Carter, isolation) | pilot-prerequisite; sketch useful pre-pitch |
| 7 Competitor objection matrix | Jarred | before 7/17 (prep); INTERNAL, not investor-facing |
