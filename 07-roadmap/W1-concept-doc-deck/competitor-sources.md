# Competitor sources: first sourcing pass (W1, counsel verdict 12)

**Next review due 2026-08-08.** Monthly competitive-review cadence (W10 task 10.4) is seeded by this pass; each review re-checks the sourced moves below, retries the do-not-render list, and works the not-yet-searched queue.

**Compiled:** 2026-07-08, web sourcing pass for the section 13 render blocker in `concept-doc-draft-v1.md`.
**Rule:** every named move in any rendered artifact carries a source a skeptic can click. Anything in the do-not-render list stays out of every rendered version entirely.

**Tag scheme (task mapping, reconciled with the repo's honest-math lineage):**

- MEASURED: dated event confirmed by the actor's own primary publication (press release, product blog, official docs) plus independent coverage.
- VENDOR: performance figure the vendor claims about itself (ARR, user counts, growth rates); company-disclosed, not independently audited.
- SURVEY: analyst, legal, or press reporting is the strongest available source for the fact.
- [unverified]: weak or secondhand-only sourcing; do not render.

A single move can carry two tags: the event MEASURED, the attached metric VENDOR. Both are shown where they differ.

---

## 1. Sourced moves, cleared for render

### Cognition (Devin), the move already cited in section 13

| Claim (one line) | Source | Publisher | Date | Tag |
|---|---|---|---|---|
| Cognition raised $1B+ at a $25B pre-money ($26B post) valuation, Series D | https://techcrunch.com/2026/05/27/ai-coding-startup-cognition-raises-1b-at-25b-pre-money-valuation/ and https://cognition.com/blog/series-d | TechCrunch; Cognition (own blog) | 2026-05-27 | MEASURED |
| Devin at a $492M ARR run-rate, up from $37M a year earlier; company-disclosed, not audited | https://techcrunch.com/2026/05/27/ai-coding-startup-cognition-raises-1b-at-25b-pre-money-valuation/ | TechCrunch (reporting company disclosure) | 2026-05-27 | VENDOR |

This upgrades the draft's existing "(VENDOR, secondhand, via the competitive landscape dossier)" citation to a clickable primary pair.

### Microsoft (Copilot ecosystem and the goals/OKR surface)

| Claim (one line) | Source | Publisher | Date | Tag |
|---|---|---|---|---|
| Agent 365, Microsoft's control plane for governing agents, reached general availability at $15/user/month (standalone or in Microsoft 365 E7) | https://www.microsoft.com/en-us/security/blog/2026/05/01/microsoft-agent-365-now-generally-available-expands-capabilities-and-integrations/ | Microsoft Security Blog (own) | 2026-05-01 | MEASURED |
| Microsoft retired Viva Goals, its OKR product, on 2025-12-31 with no replacement; customers directed to third-party OKR tools | https://learn.microsoft.com/en-us/viva/goals/goals-retirement | Microsoft Learn (own docs) | retirement effective 2025-12-31 | MEASURED |
| At Build 2026 (June 2-3) Microsoft positioned Windows itself as a platform for building and running AI agents | https://blogs.windows.com/windowsdeveloper/2026/06/02/build-2026-furthering-windows-as-the-trusted-platform-for-development/ | Windows Developer Blog (own) | 2026-06-02 | MEASURED |

Deck relevance: the incumbent agent-governance bundle is GA now, and the incumbent exited the OKR lane rather than AI-scoring it. Both cut in our favor and both are sourced.

### Salesforce (Agentforce)

| Claim (one line) | Source | Publisher | Date | Tag |
|---|---|---|---|---|
| Agentforce ARR reached $800M (up 169% YoY) with 29,000 deals closed, per Salesforce's Q4 FY26 earnings release | https://investor.salesforce.com/news/news-details/2026/Salesforce-Delivers-Record-Fourth-Quarter-Fiscal-2026-Results/default.aspx | Salesforce investor relations (own) | 2026-02-25 | VENDOR (company-published figure in an earnings release) |
| Third-party read: roughly 5-10% of the Salesforce install base has actually signed an Agentforce deal | https://www.salesforceben.com/huge-agentforce-growth-in-salesforce-q4-as-benioff-mocks-saaspocalypse-narratives/ | Salesforce Ben (analyst commentary citing Stifel/SaaStr) | 2026-02/03 | SURVEY |

### ClickUp (Brain / Super Agents)

| Claim (one line) | Source | Publisher | Date | Tag |
|---|---|---|---|---|
| ClickUp ships Super Agents, AI teammates that hold workspace identity, memory, and 500+ skills, in the Everything AI tier ($28/user/month annual) | https://clickup.com/brain/agents and https://help.clickup.com/hc/en-us/articles/31010910371991-What-are-Super-Agents | ClickUp (own product/docs) | live as of this pass; launched Dec 2025 per third-party coverage | MEASURED (existence and pricing), VENDOR (capability claims) |
| Brain² update lets ClickUp autonomously spin up dedicated agents for recurring tasks, with multi-model routing (Claude, ChatGPT, Gemini) | https://cryptobriefing.com/clickup-brain-ai-autonomous-agents/ | Crypto Briefing (press) | 2026-05-12 | SURVEY |

### Meeting-capture field

| Claim (one line) | Source | Publisher | Date | Tag |
|---|---|---|---|---|
| Otter.ai faces a consolidated federal wiretap/CIPA class action (In re Otter.AI Privacy Litigation, N.D. Cal.); motion to dismiss argued 2026-05-20, no ruling yet, no class certified | https://www.recordinglaw.com/news/otter-ai-wiretap-lawsuit-explained/ and https://www.npr.org/2025/08/15/g-s1-83087/otter-ai-transcription-class-action-lawsuit | Recording Law; NPR | hearing 2026-05-20 | SURVEY (public court record via legal press) |
| Zoom AI Companion 3.0 went GA with agentic retrieval/writing, then expanded in March 2026 to custom agents and cross-system workflow orchestration | https://news.zoom.com/zoom-launches-ai-companion-3-0/ and https://news.zoom.com/ec26-agentic-ai-platform-announcements/ | Zoom newsroom (own) | GA 2025-12-15; expansion 2026-03-10 | MEASURED |
| Granola raised a $125M Series C at a $1.5B valuation, expanding from notetaker to enterprise AI app with agent features planned | https://techcrunch.com/2026/03/25/granola-raises-125m-hits-1-5b-valuation-as-it-expands-from-meeting-notetaker-to-enterprise-ai-app/ and https://www.granola.ai/blog/series-c | TechCrunch; Granola (own blog) | 2026-03-25 | MEASURED (round), VENDOR (250% quarterly revenue growth, via Bloomberg reporting company figure) |

Deck relevance: this is the sourced backbone of the "meeting capture is commoditizing" half of section 12's threat read, plus a live legal-risk precedent that motivates our consent-first capture law.

### OKR incumbents adding AI scoring

| Claim (one line) | Source | Publisher | Date | Tag |
|---|---|---|---|---|
| WorkBoard acquired Quantive, consolidating the two largest enterprise OKR vendors | https://www.businesswire.com/news/home/20250528302450/en/WorkBoard-Acquires-Quantive-to-Strengthen-Its-Strategy-Execution-and-OKR-Software-Advantage-and-Accelerate-Innovation | Businesswire (company release) | 2025-05-28 | MEASURED |
| WorkBoard sells an "AI Chief of Staff" agent that runs the OKR cycle, drafts OKRs, and generates exec briefs; also listed on Workday Marketplace | https://www.workboard.com/products/chief-of-staff-agent and https://marketplace.workday.com/en-US/apps/537034/chief-of-staff/overview | WorkBoard (own product page); Workday Marketplace | live as of this pass | MEASURED (existence), VENDOR (capability claims) |

Deck relevance: the direct language collision with any "chief of staff" framing is real and sourced; assume the buyer has seen a WorkBoard-style pitch.

### Gamification-backlash precedent (section 8/13 requirement)

| Claim (one line) | Source | Publisher | Date | Tag |
|---|---|---|---|---|
| A Meta employee's internal AI-token leaderboard (85,000+ employees, 73.7T tokens in ~30 days) was taken down two days after press exposure; CTO Bosworth: "token usage alone is not a measure of impact of any kind" | https://fortune.com/2026/04/09/meta-killed-employee-ai-token-dashboard/ | Fortune | 2026-04-09 | SURVEY |
| Meta is replacing leaderboard culture with centralized cost monitoring ("AI Gateway") as internal AI spend tracks toward billions | https://mlq.ai/news/meta-caps-internal-ai-token-spending-after-costs-approach-billions-in-2026/ | MLQ News | 2026 (post-April) | SURVEY |

Deck relevance: this is the documented backlash precedent section 13 requires, presented alongside our answer: outcome-scored, comp-decoupled, anti-abuse from day one. We score outcomes against objectives, never raw usage; the Meta episode is the case for exactly that design law.

### Frontier-lab consulting joint ventures (the companion-category context)

| Claim (one line) | Source | Publisher | Date | Tag |
|---|---|---|---|---|
| Anthropic launched a $1.5B enterprise AI services company with Blackstone, Hellman & Friedman, and Goldman Sachs, embedding Anthropic engineers in portfolio companies | https://www.anthropic.com/news/enterprise-ai-services-company and https://www.cnbc.com/2026/05/04/anthropic-goldman-blackstone-ai-venture.html | Anthropic (own); CNBC | 2026-05-04 | MEASURED |
| OpenAI launched the OpenAI Deployment Company ($4B at $10B pre-money, TPG-led consortium) and is acquiring Tomoro (~150 forward-deployed engineers) | https://openai.com/index/openai-launches-the-deployment-company/ | OpenAI (own) | 2026-05-11 | MEASURED |
| Accenture Edge and Google Cloud launched pre-built agentic AI solutions for mid-market companies ($300M-$3B revenue) | https://newsroom.accenture.com/news/2026/accenture-edge-and-google-cloud-bring-scalable-agentic-ai-solutions-to-mid-market-companies | Accenture newsroom (own) | 2026-07-07 | MEASURED |

Deck relevance: sourced proof of the section 3 premise. The labs and integrators are entering the transition-companion motion themselves; capability plus capital is the market premise, and the differentiated stack (scored objectives, consented mechanics, earned autonomy) is what none of these ventures sells.

### Incumbent agent platforms (section 12 threat-read support)

| Claim (one line) | Source | Publisher | Date | Tag |
|---|---|---|---|---|
| ServiceNow replaced five legacy tiers with three AI-native tiers, bundling AI Control Tower, Now Assist, and Workflow Data Fabric into every tier | https://www.techtarget.com/searchitoperations/news/366641692/ServiceNow-AI-pricing-change-takes-on-enterprise-ROI-struggles and https://www.servicenow.com/products/ai-control-tower.html | TechTarget; ServiceNow (own) | 2026-04-09 | MEASURED |
| Google made the Gemini Enterprise Agent Platform GA at Cloud Next '26, absorbing Vertex AI as the single enterprise agent environment | https://cloud.google.com/blog/products/ai-machine-learning/introducing-gemini-enterprise-agent-platform | Google Cloud blog (own) | 2026-04-22 | MEASURED |
| EY deployed EY.ai EYQ to 300,000+ professionals with 50,000+ agents developed in nine months (self-published case study; counts self-reported) | https://www.ey.com/en_us/insights/ai/building-an-enterprise-scale-agentic-ai-operating-system | EY (own case study) | published 2026 (Apr-May) | MEASURED (deployment), VENDOR (counts) |
| Asana acquired StackAI (~$75M per press) to add cross-system agent execution; AI Teammates GA April 2026 at $15/user/month | https://asana.com/press/releases/pr/asana-acquires-stackai-adding-cross-system-execution-for-human-agent-teams/e7c73b97-ae8c-4e51-b927-189ccb184146 and https://techcrunch.com/2026/05/28/asana-acquires-no-code-agent-builder-stack-ai/ | Asana (own); TechCrunch (price) | 2026-05-28 | MEASURED (deal), SURVEY (price) |

### Funded specialists circling the whitespace

| Claim (one line) | Source | Publisher | Date | Tag |
|---|---|---|---|---|
| Dust raised a $40M Series B (Sequoia/Abstract co-led, Snowflake and Datadog participating) for "multiplayer" enterprise AI agents | https://www.axios.com/pro/enterprise-software-deals/2026/05/18/agentic-ai-dust-snowflake-sequoia and https://dust.tt/blog/series-b-multiplayer-ai | Axios; Dust (own blog) | 2026-05-18 | MEASURED (round), VENDOR (240% net revenue retention, zero 2025 churn) |
| Sierra raised $950M at a $15.8B post-money valuation (Tiger Global and GV led) | https://techcrunch.com/2026/05/04/sierra-raises-950m-as-the-race-to-own-enterprise-ai-gets-serious/ and https://www.cnbc.com/2026/05/04/bret-taylor-sierra-fundraise-openai.html | TechCrunch; CNBC | 2026-05-04 | MEASURED (round), VENDOR ($150M ARR in eight quarters) |
| Glean announced passing $300M ARR (own press release; part is consumption run-rate, not strictly recurring) | https://www.glean.com/press/glean-surpasses-300m-arr-unrivaled-enterprise-context-fuels-ai-adoption and https://techcrunch.com/2026/05/28/gleans-top-line-crosses-300m-as-ai-budget-cutting-becomes-its-major-selling-point/ | Glean (own); TechCrunch | 2026-05-28 | VENDOR |
| Bond (YC X25) sells "Donna," an AI chief of staff for CEOs: presidential brief, live KPI dashboard, org-wide pulse | https://www.ycombinator.com/companies/bond | Y Combinator company page | live as of this pass | MEASURED (existence; funding undisclosed) |

---

## 2. Could not source: DO NOT RENDER

These claims appear in the dossiers or the pending block but did not clear the clickable-source bar in this pass. They stay out of every rendered artifact until a future review sources them.

| Claim | Why blocked | Retry at next review |
|---|---|---|
| Lattice "AI Leverage Insights" (token-burn-vs-output scoring) as the closest shipped gamification analog | Not verified this pass; no primary source on file | yes |
| Amazon "KiroRank" leaderboard deprecated 2026-05-29 | Only a passing secondary mention ("Amazon shut down its own leaderboard after employees gamed it") in Meta-episode coverage; product name and date unconfirmed | yes |
| Uber and Tesla per-employee AI budget caps (specific dollar/week figures) | Secondary mentions only in Meta-episode coverage; no primary source for the specific caps | yes |
| Otter.ai "35M+ users" | User count not confirmed this pass (litigation is sourced above; the user figure is not) | yes |
| Anthropic Cowork / Managed Agents launch-and-GA timeline specifics (Jan 2026 preview, Apr 9 GA, Jul 7 web/mobile) | Dossier-carried dates not re-verified this pass | yes |
| "One new platform move every 5-6 weeks" lab cadence | Analytic characterization, not a sourceable fact; never render as a stat | reframe or drop |
| Slack (Claude in Slack), Notion, Linear, Atlassian specific agent moves | Not searched this pass | yes |
| WorkBoard post-merger growth figures (30% YoY, 50% QoQ) | Company-claimed in own newsroom only; not load-bearing for the deck | optional |
| Any "6-9 months" (or any month-count) whitespace window | Hard law: no unsourced time precision; the whitespace claim renders without a clock | no (policy) |

---

## 3. Section 13 render-blocker resolution map

| Pending-block item | Status |
|---|---|
| Cognition (Devin) move | CLEARED, upgraded to primary sources |
| Microsoft (Copilot and its goals/OKR surface) | CLEARED (Agent 365 GA; Viva Goals retirement, no replacement) |
| Salesforce (Agentforce) | CLEARED (Q4 FY26 earnings release; VENDOR tag mandatory on the ARR figure) |
| ClickUp (Brain) | CLEARED (own product/docs pages; Brain² via press) |
| Meeting-capture field (Otter, Zoom AI Companion, Granola class) | CLEARED (all three sourced) |
| OKR incumbents adding AI scoring | CLEARED (WorkBoard/Quantive plus shipped AI Chief of Staff agent) |
| Documented gamification-backlash precedent | CLEARED (Meta token-leaderboard episode, Fortune 2026-04-09) |

Everything else named in the dossiers either has a sourced row above or sits in the do-not-render list. The section 13 bar holds: what can't meet it doesn't get said.
