# Comparable-vendor pricing scan (task 8.4)

**Workstream:** W8 unit economics + ICP (counsel blind spot 1) | **Task:** 8.4 | **Authored:** 2026-07-08
**Status:** done, research-loop output. Feeds 8.2 (pricing model options) and 8.5 (one-page summary). No founder gate.
**Retrieval date for ALL web-sourced figures: 2026-07-08.** Pricing changes frequently; re-verify on the vendor page before any figure goes into a client-facing or deck-bound artifact.

**Lineage legend:** MEASURED = internally observed in the reference implementation or a signed engagement. SURVEY = third-party study/survey. VENDOR = vendor-published figure (from the vendor's own page or listing). VENDOR (secondhand) = a vendor's price as reported by a third-party pricing analysis, review site, or transaction-data aggregator; the vendor itself is sales-gated or the figure was not confirmed on the vendor's own page. [unverified] = inference or unconfirmed claim.

**Framing law:** the product is UNNAMED. These vendors are comparables for pricing shape and budget-line calibration, not a feature-parity claim. Per the whitespace law (CLAUDE.md), no single vendor below occupies the OKR-scoring + gamification + attribution stack together; that claim is argued elsewhere and is not this document's job.

---

## 1. Why these five categories

The concept spans several existing budget lines. Each category below is a lane the domino-1 or domino-2 buyer already pays into, so its pricing anchors what "normal" looks like on that line (ICP doc section 2, `icp-definition-v1.md`):

1. AI chief-of-staff / executive-assistant tools: the literal descriptor of the domino-1 seat.
2. Meeting-intelligence tools: the capture layer (pilot days 1-30 scope).
3. Enterprise AI assistants: the procurement-led shape we are explicitly NOT at domino-1 (calibrates the ceiling and the wrong shape).
4. OKR platforms and gamified-performance platforms: the days 31-90 scope and the domino-3 whole-org tier.
5. AI-transformation consulting and fractional-executive services: the consulting-revenue-first spine and the human-alternative anchor.

## 2. AI chief-of-staff / executive-assistant tools

| Vendor / tier | Price | Lineage | Source |
|---|---|---|---|
| Motion (Individual, annual) | $19/mo | VENDOR (secondhand) | get-alfred.ai roundup, https://get-alfred.ai/blog/best-ai-chief-of-staff-tools |
| Notion AI | $20/seat/mo | VENDOR (secondhand) | same roundup |
| alfred_ | $24.99/mo ($249/yr) | VENDOR | https://get-alfred.ai/blog/how-much-should-an-ai-assistant-cost |
| Carly | $35/mo | VENDOR | https://www.usecarly.com/blog/best-ai-chief-of-staff/ |
| Lindy | $49.99/mo Plus, $99.99 Pro, $199.99 Max | VENDOR (secondhand) | get-alfred.ai pricing map, https://get-alfred.ai/blog/how-much-should-an-ai-assistant-cost |
| readywhen | free Personal, $49/mo Business, $99/mo Business Pro | VENDOR | https://readywhen.ai/blog/best-ai-chief-of-staff-tools-2026 |
| Coworker | $30/user/mo | VENDOR (secondhand) | readywhen roundup, same URL |
| Category band (personal tier) | $19-50/seat/mo | VENDOR (secondhand, aggregated) | both roundups above |
| Xembly, Bond, Ambient | sales-led, custom quote, no public price | VENDOR (secondhand) | readywhen roundup |

**Read:** the self-serve "AI chief of staff" category prices as prosumer software, tens of dollars a month. None of it carries delivery, org integration, or a human gate posture; the category's own marketing concedes the judgement half of the role is uncovered ("no software is close in 2026", get-alfred.ai pricing map, retrieved 2026-07-08). This is the noise floor, not our comparable. Our comparable set for the domino-1 seat is section 6 (consulting + fractional executive), because the engagement is consultative delivery, not a seat license.

## 3. Meeting-intelligence tools (the capture layer)

| Vendor / tier | Price | Lineage | Source |
|---|---|---|---|
| Otter.ai Pro | from $8.33/user/mo annual ($16.99 monthly) | VENDOR (secondhand) | https://summarizemeeting.com/en/faq/meeting-ai-cost-comparison |
| Otter.ai Business | $20/user/mo annual | VENDOR (secondhand) | same |
| Fireflies Pro | $10/user/mo annual ($18 monthly) | VENDOR (secondhand) | https://get-alfred.ai/blog/fireflies-pricing |
| Fireflies Business | $19/user/mo annual ($29 monthly) | VENDOR (secondhand) | same |
| Fireflies Enterprise | $39/user/mo annual | VENDOR (secondhand) | same |
| Fireflies AI-credit add-ons | $5 per 50 credits, up to $600 per 10,000 | VENDOR (secondhand) | same |
| Fathom Team Edition | ~$19/user/mo annual (generous free tier) | VENDOR (secondhand) | https://www.granola.ai/blog/meeting-note-tool-pricing-granola-vs-fireflies-fathom-otter |
| Gong | custom only; est. $1,200-1,600/seat/yr + $5,000-15,000 platform fee; avg contracts $50K+/yr | VENDOR (secondhand estimate) | https://nimitai.com/blog/conversation-intelligence-pricing-2026 |
| Mid-market conversation intelligence (Avoma, Salesloft, Jiminny) | $79-165/seat/mo | VENDOR (secondhand, aggregated) | same |

**Read:** commodity capture is $10-30/user/mo and racing to free (Fathom's free tier is unlimited recording). Value-priced capture exists only where it is tied to a revenue workflow (Gong at $50K+ contracts). Consequence for us: meeting capture alone cannot carry price; it is table stakes inside a larger engagement. This matches the loop-deletion framing law: we price the deleted loop, not the transcript.

## 4. Enterprise AI assistants (the shape we are not, at domino-1)

Refreshes the Glean/Moveworks figures the ICP doc inherited from `03-execution/pilot-design.md`.

| Vendor | Price shape | Lineage | Source |
|---|---|---|---|
| Glean | ~$50-75/user/mo, ~100-seat minimum (~$60K/yr ACV floor); hybrid model reported as $45-50 base + $15/user/mo AI add-on + consumption FlexCredits | VENDOR (secondhand) | https://www.gosearch.ai/blog/glean-pricing-explained/ ; https://checkthat.ai/brands/glean/pricing |
| Glean TCO | first-year totals $300K to $1M+; support fees ~10% of subscription; implementation $50K-250K+ | VENDOR (secondhand) | https://workativ.com/ai-agent/blog/glean-pricing |
| Moveworks (now ServiceNow; acquisition closed Dec 2025) | flat annual fee by headcount; AWS Marketplace lists $150/user/yr for 1,000-2,500 employees; Vendr transaction data shows $200K-600K ACV at 1,000-5,000 employees (~$20-40/employee/yr); median ACV ~$130K | VENDOR (secondhand) | https://www.vendr.com/marketplace/moveworks ; https://workativ.com/ai-agent/blog/moveworks-pricing |
| Moveworks implementation | $50K-200K | VENDOR (secondhand) | https://workativ.com/ai-agent/blog/moveworks-pricing |

**Read:** unchanged from the ICP conclusion, now with fresher numbers. These are procurement-led, seat-floored, six-figure-TCO purchases with 8-16 week deployments. Wrong shape for a single-executive relationship-anchored seat; right calibration for what domino-3 whole-org software pricing can eventually look like ($200K-600K/yr at mid-market headcounts is a proven willingness-to-pay band).

## 5. OKR platforms and gamified-performance platforms (days 31-90 scope, domino-3 tier)

### OKR platforms

| Vendor / tier | Price | Lineage | Source |
|---|---|---|---|
| Lattice | from $11/person/mo performance + $6 OKR add-on (~$17 combined); full suite from ~$19 | VENDOR (secondhand) | https://www.tability.io/compare/vs/15five-vs-lattice ; https://www.tability.io/odt/articles/okr-software-pricing-comparing-the-top-17-okr-vendors |
| 15Five | Engage $4, Perform $11, Total Platform $16/user/mo annual (one source cites $14; verify with vendor) | VENDOR (secondhand) | https://www.tability.io/odt/articles/okr-software-pricing-comparing-the-top-17-okr-vendors |
| Perdoo | Premium $9/user/mo; free to 10 users | VENDOR (secondhand) | same |
| Betterworks | custom quote; G2/Capterra estimates $8-15/user/mo, enterprise deployments, no free trial | VENDOR (secondhand estimate) | https://peopleopsclub.com/software/betterworks/pricing |
| Quantive, Workboard | custom quote, $15+/user/mo band | VENDOR (secondhand estimate) | https://www.tability.io/odt/articles/okr-software-pricing-comparing-the-top-17-okr-vendors |
| Category band | ~$7-15/user/mo mid-market; scaling math: $9/user/mo = $10,800/yr at 100 people | VENDOR (secondhand, aggregated) | same |

### Gamified performance

| Vendor / tier | Price | Lineage | Source |
|---|---|---|---|
| Spinify | $25/user/mo base on Salesforce AppExchange; practical tiers $40-65/user; 15-seat minimum (~$4,500/yr floor); reviews show $9-70 quotes for the same product | VENDOR + VENDOR (secondhand) | https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3A00000DqDQnUAN&tab=e&cta=demo ; https://prospeo.io/s/spinify-pricing-reviews-pros-and-cons |
| SalesScreen, Ambition | sales-gated; $25-50/user/mo band, annual contracts, seat minimums | VENDOR (secondhand estimate) | https://croclub.com/tools/best-sales-gamification-software/ |
| Centrical | enterprise custom quote, no public price surfaced | [unverified] as to level | https://pearllemonsales.com/best-sales-gamification-platforms-2026/ |
| Category band | $15-50/user/mo, moved upmarket in 2026 with seat minimums | VENDOR (secondhand, aggregated) | https://www.guideflow.com/blog/best-sales-gamification-software |

**Read:** OKR software is a $7-15/user/mo commodity line; gamification adds a $25-50/user/mo premium lane but only for sales orgs today. Nobody prices the combined OKR-scoring + gamification + attribution stack as one product at the org level (consistent with the whitespace read, to be presented reconciled with the commoditization threat per CLAUDE.md). For 8.2: the per-user software ceiling at domino-3 is roughly $20-50/user/mo against these anchors unless the engagement is outcome-priced instead.

## 6. AI-transformation consulting and fractional-executive benchmarks (the spine)

### Consulting rates and engagement sizes

| Benchmark | Figure | Lineage | Source |
|---|---|---|---|
| MBB hourly | $500-1,000+/hr; blended $300-500/hr | VENDOR (secondhand, aggregated rate guides) | https://aidolsgroup.com/en/blog/category/research-report/ai-consulting-cost-guide/ ; https://bosio.digital/articles/ai-consulting-cost-guide |
| Big 4 hourly | $300-600/hr | VENDOR (secondhand) | same |
| Mid-tier (Accenture, IBM, Capgemini) | $250-500/hr | VENDOR (secondhand) | same |
| Boutique / independent AI firms | $150-350/hr (specialist boutiques $100-200 blended) | VENDOR (secondhand) | https://www.groovyweb.co/blog/ai-consulting-rates-2026 ; https://dataconsultingfirms.com/insights/ai-consulting-pricing |
| AI readiness assessment | $2,500-75,000 | VENDOR (secondhand) | https://bosio.digital/articles/ai-consulting-cost-guide |
| AI proof of concept | $20,000-250,000 | VENDOR (secondhand) | same |
| Mid-market AI program | $35,000-150,000 | VENDOR (secondhand) | same |
| Enterprise AI transformation | $500K start, frequently $1M+, up to $5M+ multi-year | VENDOR (secondhand) | same ; https://dataconsultingfirms.com/insights/ai-consulting-pricing |
| MBB 4-8 week AI strategy sprint | $150K-750K | VENDOR (secondhand) | https://aidolsgroup.com/en/blog/category/research-report/ai-consulting-cost-guide/ |
| Boutique doing comparable transformation work | $50K-300K vs Big 4 $200K-2M+ | VENDOR (secondhand) | https://foundersworkshop.com/feeds/blog/ai-enterprise-consulting-rates-500 |
| Outcome-linked fees | ~1 in 4 of McKinsey's global fees now tied to outcomes, not hours (piloting since late 2025) | VENDOR/press | https://www.thestreet.com/markets/ai-is-forcing-mckinsey-bcg-bain-to-rethink-consulting-fees |
| Rate trend | AI consulting rates up 10-15% YoY since 2024 | SURVEY (secondhand) | https://rockstardeveloperuniversity.com/ai-consulting-rates-statistics/ |
| Buyer-side overrun | ~42% of AI consulting engagements exceed original budget; buyers advised to budget 20-40% above quote | SURVEY (secondhand) | https://bosio.digital/articles/ai-consulting-cost-guide |

### Fractional / human chief-of-staff anchor (the human alternative for the domino-1 seat)

| Benchmark | Figure | Lineage | Source |
|---|---|---|---|
| Fractional chief of staff retainer (US) | $7,000-14,000/mo | VENDOR (secondhand, marketplace benchmark) | https://fractionus.com/blog/fractional-executive-rates-by-role |
| Fractional chief of staff hourly | avg $170/hr; 25th-75th percentile $130-200/hr; typical engagement ~25-27 hrs/wk; ~$17K/mo at full scope | VENDOR (marketplace's own data) | https://www.gofractional.com/insights/rates/chief-of-staff |
| Fractional executives generally (US) | $8,000-22,000/mo | VENDOR (secondhand) | https://fractionus.com/blog/fractional-executive-cost-us-2026 |
| Full-time chief of staff, true employer cost | $240,000-265,000+/yr (avg base ~$185K) | VENDOR (secondhand) | https://fractionus.com/blog/fractional-executive-rates-by-role |
| Human executive assistant | $75,000-150,000/yr | VENDOR (secondhand) | https://get-alfred.ai/blog/how-much-should-an-ai-assistant-cost |
| "AI Chief of Staff" executive-role salary | $200K-350K base (Series B+ and large enterprise, June 2026) | VENDOR (secondhand; pre-existing citation) | valueaddvc.com via `03-execution/pilot-design.md` |
| General enterprise AI pilot | $50K-200K over 8-16 weeks | SURVEY (aggregated web synthesis, secondhand; pre-existing citation) | via `03-execution/pilot-design.md` |

**Read:** the consulting lane is where our engagement actually lives, and it prices two orders of magnitude above the software lanes. A 90-day design-partner pilot priced anywhere in the $50K-250K envelope sits inside three independently sourced bands at once: the general AI-pilot band, the boutique-transformation band, and the mid-market AI-program band. The fractional chief-of-staff retainer band ($7-14K/mo) plus the true cost of the full-time hire ($240K+/yr) is the budget line the domino-1 CEO already understands. The McKinsey outcome-fee shift is category air cover for milestone- and outcome-shaped pricing.

## 7. Internal anchors (for cross-reference in 8.2)

- MEASURED: one signed $25K/mo consulting retainer with the closest live reference relationship (`01-overview/product-concept-overview-2026-07-08.md` section 7; `02-sweep/swarm-client-relationships.md`). This is the only internally proven price point.
- [unverified]: the floated "$15K + 50bps" agentic-consulting structure exists as an auto-generated opportunity-brief thesis only, never quoted or signed (`01-overview` section 8). Not usable as precedent.
- VENDOR (secondhand, pre-existing): Cognition/Devin outcome-shaped pricing (PRs merged), $492M ARR run-rate, as domino-2 engineering-lane precedent (`04-competitive/landscape-consulting-hybrids.md`).

## 8. What this hands to 8.2

1. **Anchor in the consulting lane, not the software lane.** Software comparables cap at tens of dollars per seat; consulting comparables start at tens of thousands per engagement. The MEASURED $25K/mo retainer sits comfortably inside the boutique band ($300K/yr run-rate vs the $50K-300K boutique-transformation band and the $8-22K/mo fractional-executive band's top end).
2. **The human-substitution story is arithmetically clean:** $25K/mo is roughly the fully loaded monthly cost of the full-time chief of staff the buyer would otherwise hire ($240K-265K/yr true cost), and it is inside the fractional band once scope is counted. Same budget line, same order of magnitude, more coverage.
3. **Outcome/milestone pricing has category legitimacy** (McKinsey 1-in-4 outcome-linked; Devin PRs-merged), which supports milestone-based structures and the equity+cash default without looking exotic.
4. **Software-line pricing enters at domino-2/3, not domino-1,** with proven bands: $20-50/user/mo (OKR + gamification stacked) up to $200-600K/yr ACV (enterprise assistant shape at mid-market headcounts).
5. **Pilot envelope sanity check:** $50K-200K for 8-16 weeks is the externally quoted normal. A 90-day design-partner pilot priced below or at the bottom of that band is defensible as deliberately concessionary for a design partner; far above it needs justification.

## 9. Gaps and cautions

- Most figures above are VENDOR (secondhand): third-party pricing analyses of sales-gated vendors. Before any figure appears in a client-facing or deck-bound artifact, confirm on the vendor's own page as of that day (hard law: honest math).
- Centrical pricing never surfaced publicly; its level is [unverified].
- The Gong per-seat and platform-fee figures are estimates by a competitor-adjacent analysis; treat as directional only.
- No vendor was found selling the combined stack (OKR scoring + gamification + attribution) at the org level; absence of evidence here is consistent with the whitespace claim but is not proof of it, and must be presented reconciled with the 2-of-7-pillars-commoditized threat read (CLAUDE.md hard law).
- All retrievals 2026-07-08; the meeting-intelligence and AI-assistant categories reprice quarterly or faster.
