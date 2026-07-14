# Fundraising Path: Structuring a $10-50M Raise from Allan Marshall

> [CAVEAT, W0 hygiene 2026-07-08: written PRE-Upexi-correction. Per CLAUDE.md correction 3 this initiative is COMPLETELY SEPARATE from Upexi; any passage premised on Upexi the company (UPXI investor-capacity math, Upexi pilot scoping, Upexi-specific MNPI framing) is INVALID AS PREMISED. Corrected view: overview section 12 + counsel verdicts. Alan is engaged in a personal, separate capacity.]


**Angle:** fundraising-path
**Date:** 2026-07-08
**Time-boxed research (~12 min) combining local estate evidence with live web research.**

---

## Headline

The single biggest unresolved fact is not the legal instrument, it is who is actually writing the check. The internal docs say "Allan Marshall (Upexi CEO) for $10-50M," but Marshall personally owns about 4.5% of Upexi worth roughly $13M (dated data point, see Sources), which is not enough on its own to fund a $50M check without leverage, a syndicate, or Upexi's own balance sheet. Marshall's own playbook, the $100M Solana treasury PIPE he ran through Upexi in April 2025, was a lead-investor-plus-syndicate structure (GSR led; Delphi, Morgan Creek, White Star Capital, Hivemind, and others followed; Marshall added a personal check alongside them), not a single-check-writer move. The recommendation below is built around that precedent: treat this as a personal-or-syndicate-led priced round into a clean NewCo, tranche it against the product's own stated gaps, and keep Upexi-the-public-company off the cap table and off the balance sheet unless and until it becomes a paying customer.

---

## Findings

### 1. Who Allan Marshall actually is, and why that matters structurally

Allan Marshall is CEO, President, and Chairman of Upexi, Inc. (NASDAQ: UPXI). He founded and formerly ran XPO Logistics before joining Upexi in 2019. His total compensation is reported around $1.09M/year (77% salary, 23% bonus/stock). He directly owns about 4.5% of Upexi's shares, reported at roughly $13.21M (Simply Wall St figure, likely priced off a different date than the December 2025 insider-buy prints below, so treat as approximate, not load-bearing). He is an active, disclosed insider trader in his own stock: he bought 100,000 shares at $2.07 on December 15, 2025, 50,000 more at $2.07 on December 16, and 50,000 more at $1.80 on December 23, 2025.

Upexi itself pivoted in 2025 from a consumer-products brand owner into a Solana-based crypto treasury company. In April 2025 it closed a $100M private placement (PIPE) led by GSR, priced above the last market close under Nasdaq rules, with participation from Big Brain, Anagram, Delphi Ventures, White Star Capital, Maelstrom (Arthur Hayes's family office), Hivemind, Borderless, Morgan Creek, Elune Capital, Delta Blockchain Fund, several named crypto angels, and Marshall himself as a personal co-investor. It raised a further ~$10M private placement later in 2025 and authorized a $50M share buyback on November 13. This is directly relevant: it shows Marshall's operating pattern is "lead-plus-syndicate, priced above market, staged capital deployment, CEO co-invests personally," not "one man writes one enormous check alone."

**Implication:** before locking any structure, Jarred needs a direct answer to one question: is the $10-50M meant to come from Marshall's personal balance sheet, a syndicate he assembles (plausibly drawing on the same crypto-VC bench he just worked with), or Upexi's corporate treasury. Each answer implies a materially different instrument and timeline, detailed below.

### 2. Structure comparison: SAFE vs priced round vs JV vs NewCo-with-strategic-anchor

- **SAFEs** dominate small, fast, founder-friendly rounds. On Carta's data, SAFEs were roughly 90% of pre-seed deals in Q1 2025, but rounds above $5M flip decisively toward priced equity (about 70% priced, 20% SAFE). SAFE investors typically get no board seat and no real governance until conversion, a poor fit for an operator like Marshall who will almost certainly want influence, not just upside. (Sources: carta.com, CRV, Capitaly.)
- **Priced rounds** give the investor a defined stake, preferred-stock protections, and (usually) a board or observer seat immediately. Legal cost and speed, historically the argument against priced rounds at this stage, have dropped: platforms like Carta, SeedLegals, and AngelList Stack now turn a priced round around in weeks, not months. This is the better fit for a strategic writing a check this size who wants governance now, not at a future conversion event.
- **Joint venture (new jointly owned entity)** fits when the strategic wants operational co-building, shared risk on a specific initiative, and pre-agreed exit points, and is willing to trade passive-investor simplicity for hands-on involvement. It is the heaviest structure to stand up and the hardest to unwind.
- **NewCo with a strategic anchor** (a fresh cap-table entity that absorbs the IP and receives the priced-round investment) is the middle path: it gives Marshall real governance and economics without forcing Upexi's own reporting entity onto the cap table, and it cleanly separates the raise from Jarred's personal consulting practice and from unrelated ventures (Mima).

Anchor-investor literature flags the control risk of any single, dominant, non-diversified check writer: "a really dominant anchor means you have a boss," and anchor checks that come with committee-style influence can crowd out a future institutional lead's usual terms (Teten; Umbrex). The standard anchor check-size rule of thumb in early-stage rounds is 20-30% of the round target, with the anchor typically also taking the lead/board role; a $10-50M ask concentrated in one relationship is well outside that norm and should be treated as a real structural risk, not just a governance footnote.

### 3. Comparable operator-led agentic-AI raises, 2024-2026

None of the deals found are a clean precedent for "single HNW/strategic check, concept stage, consulting+software hybrid." The market's actual comps are institutional-fund-led:

- **General Analysis**, $10M seed (April 2026), led by Altos Ventures with 645 Ventures, Menlo Ventures, and Y Combinator, for agentic-AI security infrastructure. Founding team drawn from NVIDIA/Cohere/DeepMind/Harvard/Caltech research backgrounds.
- **Convey**, $38M from Andreessen Horowitz for enterprise "AI teammates," but only after reaching $50M ARR within seven months, i.e., revenue-validated, not concept-stage. Not a fair comp for where this product is today.
- **Pie**, $19.5M from Lightspeed, AI receptionists for small businesses.
- **Sail Research**, $80M raise at a $450M valuation (Kleiner Perkins, Sequoia) for agent inference infrastructure, an outlier on both size and valuation.
- **Trase**, a $107M seed led by ARCH Venture Partners for an "agentic operating system for healthcare and defense back offices." This is the closest positioning comp (same "agentic operating system" category language) but it is backed by a tier-1 institutional science-focused fund, not a single strategic, and at a scale well beyond this team's current evidence base.

Market-wide framing: 2025 agentic-AI funding totaled about $6.42B; 2026 year-to-date (through April) is about $2.66B, up 142.6% over the same period in 2025. The median seed round is roughly $9-30M; only about 13 deals in the last 12 months exceeded $50M, and those carry outsized traction signals this product does not yet have (a packaged case study, live revenue, a built multi-tenant product). Average round size actually fell from about $60M to about $36M in early 2026, suggesting the market is not getting more generous at the top end. Read plainly: a $50M number for this product today would sit at the very top of what even revenue-proven, institutionally-led agentic-AI companies are raising, and this product has no revenue of its own yet (the revenue that exists, Anchorage's $25k/mo, RoboStrategy, is Jarred's personal consulting book, not the productized Agent OS).

### 4. How consulting+software hybrids structure equity-for-services

Consulting firms with proprietary software/IP wrapped around services ("services-SaaS hybrids") command EBITDA multiples of 4-7x versus plain consulting, with a 0.5-1.5x premium over pure-services firms, and revenue multiples of 1.5-5x when private equity or strategics (cited comparables: Genstar, GTCR, Accenture, Deloitte) underwrite the deal. This is a meaningfully different valuation anchor than a venture multiple-of-nothing, and it is arguably the most defensible number Jarred actually has today: his live consulting book, not the unbuilt product, is the asset with real revenue and real multiples attached.

On equity-for-services specifically: practitioner guidance is to reserve equity for people or counterparties who move an existential needle, vest it against objective outcomes, and keep it out of recurring/operational work, because equity for routine services blurs governance and "cash beats complexity." This is a direct warning against letting Jarred's client-facing equity-for-services conversations (e.g., any equity-for-overhaul framing floated with Anchorage) bleed into the capital-raise conversation with Marshall. They should be structurally and legally separate tracks, exactly like the two are already organizationally separate in the estate (client-relationship track vs. fundraise track).

### 5. Diligence a check this size demands at concept stage

Pre-seed diligence practice (Charles Hudson/Precursor Ventures) says that at concept stage, with no revenue or customer references to check, diligence concentrates on corporate hygiene: a clean cap table with no departed-founder landmines, verified (not merely claimed) cash-in-bank, a complete picture of every SAFE or side letter outstanding, and, above a certain check size, criminal/background checks on the founding team. A $10-50M check is far above the size where that last item stays optional. Given the product overview's own scorecard, expect diligence to land hardest on:

- **IP ownership clarity.** Is "the reference implementation" (the ~15-repo personal estate) cleanly assignable to a NewCo, or is it entangled with Jarred's personal consulting LLC, other side ventures (explicitly out-of-scope: Mima, AI Coalition), and client-owned work product? This needs a clean IP assignment before any term sheet, not after.
- **Founder capacity.** Jarred is simultaneously running client delivery (Anchorage Sprint 1 launches 7/9-19, overlapping the 7/11 doc and 7/15 deck deadlines), the fundraise, and the build. A sophisticated diligence process will ask directly how one person's time is allocated across all of it.
- **The unpackaged case study.** Carter's 16x claim (4-engineer team at 16x baseline vs. an 18-engineer control at 2.5x) has no company, dataset, or methodology attached yet; it is due 7/15. Until it is packaged and defensible, it cannot be presented as evidence, only as a claim, and a diligence-savvy investor will discount it accordingly.
- **What $X actually buys.** The product's own scorecard shows real gaps: no built multi-tenancy, no per-person gamification with anti-abuse, no outcome-based OKR scoring, and zero code on the attribution/proof-of-origination pillar. A single lump-sum check with no milestone structure invites exactly the diligence pushback of "what does this buy in 12 months," and gives Jarred no leverage to justify the top of the $10-50M range.

### 6. Red flags specific to a public-company CEO as investor

- **Equity-method accounting exposure.** Under US GAAP (ASC 323, ex-APB 18), an investor holding roughly 20%+ of a company's voting stock, or holding less than 20% but also holding a board seat and information rights, is presumed to have "significant influence," which triggers equity-method accounting: Upexi would have to pick up this company's (likely large, concept-stage) losses on its own income statement. If Upexi itself is the investing entity, this is a real earnings-optics problem for a public company already carrying a new, closely-watched Solana-treasury narrative. (Sources: PwC Viewpoint, Deloitte Roadmap, KPMG Equity Method Handbook.)
- **Nasdaq Rule 5630 / Item 404 related-party exposure.** If Marshall's personal investment is ever bundled with, or made contingent on, this company later selling services back to Upexi (or to Anchorage, or any Marshall-adjacent entity), that becomes a related-party transaction requiring Upexi's audit committee to review it, and disclosure under Item 404 of Regulation S-K if it exceeds $120,000 and a related person has a material interest. Keep any future Upexi-as-customer relationship and the Marshall-as-investor relationship as fully separate, arm's-length agreements with independent consideration, exactly as Jarred already treats the Anchorage client relationship as distinct from this fundraising thread.
- **Insider-trading/MNPI hygiene.** Marshall is an active, publicly disclosed trader in his own stock (three separate buys in December 2025 alone). Nothing in the public record ties his UPXI trading to any external investment, but the closing calendar for this deal should stay clearly outside any UPXI blackout window or 10b5-1 plan mechanics, and no UPXI-specific material nonpublic information should ever enter this company's data room or vice versa.
- **Single-anchor control risk.** Anchor-investor practice literature is blunt that a large, non-diversified check writer becomes "a boss," and heavy-handed information/veto rights can make a future institutional Series A lead unwilling to prime around an already-entrenched large holder. Cap board seats, veto rights, and information/MFN rights to terms a future lead would still accept, in writing, at signing, not renegotiated later under pressure.
- **Ambiguous capital source.** As above: confirm in the room on 7/17-18, in writing, whether the check is personal, syndicate-led, or corporate. A corporate Upexi check pulls in Upexi's own board, audit committee, and Nasdaq disclosure process as a dependency, which is very unlikely to close inside the 7/15-31 internal timeline; a personal or syndicate check does not carry that dependency.
- **Open-loop relationship hygiene.** The product overview itself flags 32 pending Allan follow-ups and an unresolved Anchorage pilot-thread status. Walking into a $10-50M ask with visible open loops on the same relationship is a self-inflicted diligence red flag; sweep it first.

---

## Options considered

1. **SAFE with Marshall as an individual accredited investor.** Fast, cheap, minimal governance. Rejected as the primary instrument: wrong fit for a check this size and for an operator who will want real influence; SAFEs lose share to priced rounds well before $10M, let alone $50M.
2. **Priced equity round into a clean NewCo, Marshall as lead (personal or syndicate).** Gives Marshall real governance (board or observer seat, protective provisions, information rights) without exposing Upexi's own balance sheet or triggering equity-method consolidation. Matches Marshall's own demonstrated preference for priced, above-market, syndicate-anchored deals. This is the recommended path.
3. **Joint venture (new entity jointly owned by Upexi and the founders).** Fits only if Upexi-the-company wants operational co-ownership and a shared, in-the-box deployment (e.g., "Upexi runs on this as its own flagship case study" as a joint enterprise, not just a customer relationship). Heavier to negotiate, slower to close (misses the 7/17-18 and even 7/31 dates), and drags in Upexi's own board/Nasdaq process. Worth keeping on the table as a later, second-stage option once the product has traction, not for this initial check.
4. **Direct corporate investment from Upexi's balance sheet.** Cleanest optics for "the check came from the company," but creates the equity-method and related-party exposure described above, and risks analyst/shareholder pushback that a Solana-treasury story stock is now also allocating to illiquid private AI equity. Not recommended as the primary vehicle; if Marshall insists on it, keep Upexi's stake well under 20% voting ownership and without a board seat to preserve fair-value (not equity-method) accounting treatment.
5. **Tranched/milestone structure layered onto whichever instrument is chosen.** Not a separate structure so much as a modifier: stage the $10-50M against the product's own stated gaps (one real front-door build, per-person gamification with anti-abuse, outcome-based OKR scoring, multi-tenancy, a packaged and audited version of the 16x case study) rather than releasing it as one lump sum. This mirrors Marshall's own staged Solana accumulation and gives both sides a clean, evidence-based reason to release capital toward the top of the range rather than justifying $50M on day one.

---

## Recommendation with reasoning

**Primary recommendation: a priced equity round into a newly formed, clean-IP NewCo, with Marshall investing personally or via a syndicate he leads (not via Upexi's corporate balance sheet), tranched against the product's own gap list, closing an initial $8-15M now with the balance released against named milestones.**

Reasoning, in order of weight:

1. **The product is genuinely concept-stage** (P0 row average strength ~3.4/5 per the scorecard, attribution pillar at 0, no multi-tenancy, no outcome-based OKR scoring, no packaged case study). Market comps for institutionally-led agentic-AI rounds at this size (Trase, Sail Research, Convey) all carry either tier-1 institutional science backing or live revenue this product does not have. Asking for the full $50M in one tranche against today's evidence invites a diligence conversation the team cannot yet win. Tranching against named milestones is the honest, defensible way to keep the ceiling at $50M while only asking Marshall to underwrite what is provable today.
2. **Marshall's own operating pattern argues for this exact structure.** He personally ran a lead-plus-syndicate, priced-above-market, staged-deployment raise for his own company five months before this pitch. Pitching him a structure that mirrors his own playbook (priced, syndicate-friendly, staged capital release) is more likely to land than asking him to write a single check in a shape he has not used himself.
3. **Keeping Upexi's own reporting entity off the cap table avoids two specific, checkable landmines**: equity-method loss consolidation onto a public company's books, and Nasdaq Rule 5630 / Item 404 related-party review triggered the moment any services relationship exists alongside the investment. A personal or syndicate check from Marshall sidesteps both; a corporate check from Upexi does not.
4. **A NewCo with a clean IP assignment protects the raise from the estate's own entanglements.** The product's IP currently lives inside Jarred's personal, multi-purpose estate (shared tooling, some client-specific work, adjacent out-of-scope ventures like Mima). Diligence at this check size will not tolerate ambiguity here; assign the relevant IP into the NewCo before term sheet discussions, not after.
5. **Governance terms should be real but capped.** Marshall will want influence, not just upside, given his operator background and the size of the check; offer a board or formal observer seat and standard protective provisions, but cap veto rights and information/MFN terms to what a future institutional Series A lead would still accept, in writing, at signing.
6. **Resolve the "personal vs. corporate" ambiguity before the 7/17-18 meeting**, not during it. This single fact determines which of the above paths is even legally available and whether the 7/15/7/31 internal deadlines are realistic.

---

## Risks to this recommendation

- **Marshall may prefer, or need, to write the check through Upexi itself** (e.g., for his own tax, liquidity, or board-approval reasons), in which case the NewCo-plus-personal-investor path recommended above is not available, and the team should be ready to fall back to a capped, sub-20%, no-board-seat corporate stake to preserve fair-value accounting, accepting slower Nasdaq/board process as a cost.
- **Marshall may reject tranching** as a sign of insufficient conviction, especially given he is being pitched as a strategic partner, not a financial LP; the team should be prepared to justify tranching as protecting his downside as much as the company's discipline, and to have a credible walk-away number if he insists on one lump sum against unproven milestones.
- **The 16x case study and other pitch assets may not be ready or defensible by 7/15/7/17**, undermining the evidence base this entire tranching argument rests on; if Carter's packaged version slips, the recommended structure still works but the credible ask size shrinks correspondingly.
- **This research did not find a single true precedent** (single HNW/strategic check, concept stage, consulting+software hybrid, no institutional co-investor) to validate the recommended structure against; it is a reasoned synthesis from adjacent comps (Upexi's own PIPE, seed-market data, anchor-investor governance literature, equity-method accounting rules), not a proven playbook. Treat it as the best-available synthesis, not a market-tested template, and have counsel confirm the accounting and Nasdaq-rule conclusions before relying on them in the room.
- **Relationship risk is real and separate from structure.** The 32 open Allan follow-ups and the unresolved Anchorage pilot-thread status (flagged independently in the product overview) could color how any structure lands regardless of its technical merits; sweeping those first is a precondition, not a nice-to-have.

---

## Sources

- Carta, "What is a SAFE?" and priced-round market data: https://carta.com/learn/startups/fundraising/convertible-securities/safes/ and https://carta.com/learn/startups/fundraising/priced-rounds/
- CRV, "Priced Round vs. SAFE: How Founders Choose at Each Stage": https://www.crv.com/content/priced-round-vs-safe
- Capitaly, "Pre-Seed Round Structures: Priced Equity vs SAFE, Revisited for 2026": https://www.capitaly.vc/blog/pre-seed-round-structures-priced-equity-vs-safe-2026
- P10 Financial, "Equity Finance vs Joint Ventures: Structuring Capital": https://p10financial.com/capital/equity-finance-vs-joint-ventures
- Bradley, "Joint Venture Best Practices: A Strategic Guide for Business Leaders" (2025): https://www.bradley.com/insights/publications/2025/11/joint-venture-best-practices-a-strategic-guide-for-business-leaders-part-1
- New Market Pitch, "Agentic AI Startup Funding 2025-2026": https://newmarketpitch.com/blogs/news/agentic-ai-funding-analysis
- AgentMarketCap, "The Agentic Funding Shift: $6.42B in 2025, Fewer But Bigger Bets in 2026" (April 2026): https://agentmarketcap.ai/blog/2026/04/08/agentic-ai-funding-velocity-2026-sector-map-vertical-distribution
- Tech Startups, "General Analysis raises $10M in seed funding" (April 29, 2026): https://techstartups.com/2026/04/29/general-analysis-raises-10m-in-seed-funding-to-secure-agentic-ai-against-real-world-attacks/
- Gravity, "AI Agent Startup Funding Tracker: Q3 2026 (July Update)": https://gravity.fast/blog/ai-agent-funding-tracker-q3-2026/
- Upexi Inc. Executive Team page (Allan Marshall bio): https://ir.upexi.com/company-information/executive-team
- MarketBeat, "Upexi (NASDAQ:UPXI) CEO Allan Marshall Acquires 50,000 Shares of Stock" (December 17, 2025): https://www.marketbeat.com/instant-alerts/upexi-nasdaqupxi-ceo-allan-marshall-acquires-50000-shares-of-stock-2025-12-17/
- Daily Political, "Upexi (NASDAQ:UPXI) CEO Allan Marshall Purchases 50,000 Shares of Stock" (December 18, 2025): https://www.dailypolitical.com/2025/12/18/upexi-nasdaqupxi-ceo-allan-marshall-purchases-50000-shares-of-stock.html
- Simply Wall St, Upexi management/ownership analysis: https://simplywall.st/stocks/us/household/nasdaq-upxi/upexi/management
- Upexi IR, "Upexi Announces Pricing of $100 Million Private Placement" (April 2025): https://ir.upexi.com/news-events/press-releases/detail/101/upexi-announces-pricing-of-100-million-private-placement
- The Daily Hodl, "GSR Leads $100 Million Private Placement Into Nasdaq-Listed Upexi" (April 21, 2025): https://dailyhodl.com/2025/04/21/gsr-leads-100-million-private-placement-into-nasdaq-listed-upexi-inc-to-back-solana-based-treasury-strategy/
- The Block, "GSR helps consumer product firm Upexi create a SOL treasury with a $100 million private investment": https://www.theblock.co/post/351363/gsr-helps-consumer-product-firm-upexi-create-a-sol-treasury-with-a-100-million-private-investment
- VentureBurn, "Upexi Raises $10 Million in Private Placement Offering": https://ventureburn.com/upexi-secures-10m-solana-treasury/
- Forbes Councils, "Unlocking Growth: How Consulting Firms Can Evolve Into Software Companies" (July 7, 2025): https://www.forbes.com/councils/forbestechcouncil/2025/07/07/unlocking-growth-how-consulting-firms-can-evolve-into-software-companies/
- CT Acquisitions, "Consulting Business Valuation: 2026 EBITDA Multiples": https://ctacquisitions.com/consulting-business-valuation/
- Chudson (Charles Hudson / Precursor Ventures), "Due Diligence Checklist for Pre-Seed Companies": https://chudson.substack.com/p/due-diligence-checklist-for-pre-seed
- Kruze Consulting, "VC Due Diligence Checklist: Pre-Seed to Series B & Beyond": https://kruzeconsulting.com/blog/due-diligence-checklist/
- Y Combinator, "Series A diligence checklist": https://www.ycombinator.com/library/3h-series-a-diligence-checklist
- David Teten, "Template Structure for the Anchor Investor in Your New Private Equity/VC Fund": https://teten.com/template-structure-for-the-anchor-investor-in-your-new-private-equity-vc-fund/
- Umbrex, "Anchor Investor" glossary: https://umbrex.com/resources/private-equity-glossary/anchor-investor/
- Carta, "New VC funds are relying more than ever on their anchor investors" (2024 data): https://carta.com/data/vc-funds-anchor-investors-2024/
- altss.com, "Anchor Investors for Emerging Managers & Startups" (2025 guide): https://altss.com/blog/anchor-investors-in-early-stage-fundraising-a-comprehensive-guide
- PwC Viewpoint, "2.1 Significant influence presumption" (equity method accounting): https://viewpoint.pwc.com/dt/us/en/pwc/accounting_guides/equity_method_of_accounting/Equity_method_account/chapter_2/21_significant_influence_presumption.html
- Deloitte DART, "3.3 Other Indicators of Significant Influence": https://dart.deloitte.com/USDART/home/codification/assets/32x/asc323-10/roadmap-equity-method-investments-jv/chapter-3-applying-equity-method-accounting/3-3-other-indicators-significant-influence
- KPMG, "Handbook: Equity method of accounting" (November 2023): https://kpmg.com/kpmg-us/content/dam/kpmg/frv/pdf/2023/11.13-handbook-equity-method-of-accounting.pdf
- Securities Law Blog, "Related Party Transactions - Domestic Companies" (September 2024, Item 404/Nasdaq 5630): https://securities-law-blog.com/2024/09/24/related-party-transactions-domestic-companies/
- Legal & Compliance PLLC, "Nasdaq Corporate Governance" series (Rule 5630 discussion): https://www.legalandcompliance.com/foreign-private-issuers-sec-registration-and-reporting-nasdaq-corporate-governance-part-3/
- Perkins Coie, "Private Early-Stage Startup Companies Coming Under Increased SEC Scrutiny": https://perkinscoie.com/insights/update/private-early-stage-startup-companies-coming-under-increased-sec-scrutiny
- Local ground truth: `/Users/jarredwinn/.omnara/worktrees/miscellaneous/knelt-smugness/research/synthesis/product-concept-overview-2026-07-08.md` (feature scorecard, must-haves, open questions, especially sections 4, 6, and 9).

**Speculative/unverified flags:** whether the $10-50M is meant to be personal, syndicate, or corporate capital is not resolved anywhere in the local estate and was not found in any public source; treat every structural recommendation above as conditional on getting that answer first. The Simply Wall St ownership-value figure for Marshall's UPXI stake is dated to an unspecified pull and is inconsistent in per-share terms with the December 2025 insider-buy prices; treat it as directional only. No source was found addressing this exact deal (single strategic, concept-stage, consulting+software hybrid) directly; all structural conclusions are synthesized from adjacent precedent, not a matched comp.
