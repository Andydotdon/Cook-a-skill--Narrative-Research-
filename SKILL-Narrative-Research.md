# Narrative Research — Structured Market Validation Prompt (v3.0)

## How to Use This Prompt

This document is a **reusable instruction set** (sometimes called a "skill," "custom instruction," or "system prompt") that tells any AI assistant how to produce a structured market research document. It works with:

- **ChatGPT** (GPT-4o, GPT-4.5, o1, o3) — paste into Custom Instructions, a Project, or directly into a conversation
- **Gemini** (2.0 Flash, 2.5 Pro) — paste into a Gem, or include at the start of a conversation
- **Claude** (Sonnet, Opus, Haiku) — use as a Project prompt, paste into a conversation, or add as a skill file in Claude Code
- **Any other LLM with web search** — paste the full text as a system prompt or conversation context

**To use it**: Copy this entire document and paste it as context before your request. Then say something like *"Research the [topic] market for me."* The AI will follow the framework below.

**Without web search**: The framework still works, but the AI will rely on its training data instead of live search results. The output will note this limitation. For best results, use a model with web browsing / search enabled.

---

## Overview

This prompt produces a **structured narrative research document** — a Markdown file that validates whether an emerging market trend is real, how large the opportunity is, who the key players are, and what actionable opportunities exist.

The core philosophy is **thesis-driven validation**: start with a falsifiable hypothesis about a market trend, then systematically gather evidence to support, challenge, or refine it. This is different from generic market research (which surveys a market) or due diligence (which evaluates a specific company). Narrative research sits at the intersection — it evaluates a *story about where a market is going* and pressure-tests it with data.

**Output format**: Markdown (.md) — portable, renders in any chat interface, GitHub, Notion, Google Docs, and any Markdown viewer. No external libraries or dependencies required.

## When to Use This

Use this prompt when you want:
- A structured analysis of an emerging trend or market narrative
- Validation of whether a market opportunity is real
- A competitive landscape analysis with operational depth
- An investment thesis or opportunity assessment
- A research report that combines market data, competitive analysis, and actionable ideas

## Workflow

### Phase 1: Research

Before writing anything, conduct thorough web research on the topic. **Use your web search / browsing capability** to gather enough data to populate all 11 sections with real, cited evidence.

If you do not have web search available, state this upfront and proceed using your training knowledge — but note in the output that data freshness cannot be guaranteed.

**Search strategy — aim for at least 8 searches, often 10–15 for complex topics:**

**Layer 1: Direct topic searches (what it IS)**
1. **Core topic search**: `[topic] market growth 2025 2026` — gets market size, growth data, recent developments
2. **Key players search**: `[topic] companies funding valuation revenue` — gets competitive landscape data
3. **Market size search**: `[topic] market size TAM forecast billion` — gets analyst projections
4. **Risks and criticism**: `[topic] risks criticism challenges regulation concerns` — gets counter-narratives
5. **Per-player operational data** (repeat for each major player): `[company] revenue users metrics 2025` — gets granular execution data

**Layer 2: Problem-space searches (what problem it SOLVES)**

These searches prevent the most dangerous research blind spot: missing competitors that solve the same user problem with completely different mechanics. A bonding-curve agent trading platform and an escrow-based agent work marketplace don't share keywords — but they compete for the same user.

6. **Problem reframe search**: Strip the topic down to the *user need it serves* and search for that need directly. Ask yourself: "If the subject product didn't exist, what would the user search for?" Then search for that.
   - Template: `[user need verb] [user type] [outcome desired]`
   - Example: If researching a bonding-curve agent share platform → the user need is "AI agents transacting economically" → search `AI agent marketplace earn money transact` or `AI agent work-for-pay platform`
   - Example: If researching a DeFi yield optimizer → the user need is "earn yield on crypto passively" → search `passive crypto income alternatives [year]`

7. **Alternative solution search**: Explicitly search for different approaches to the same problem. Ask: "What are the 3 fundamentally different ways this problem could be solved?" Then search for each.
   - Template: `[problem] alternative approach OR different model OR alternative to [subject]`
   - Example: If subject uses bonding curves → search `agent economy without bonding curve` or `agent services escrow marketplace`
   - Example: If subject is a SaaS tool → search `open source alternative to [subject]` or `[problem] API-first solution`

8. **Cross-chain / cross-platform search** (for crypto/web3 topics): The subject exists on one chain/platform, but competitors may exist on completely different chains that the crypto media covers separately.
   - Template: `[concept] on [other chain/platform]` — cycle through major ecosystems
   - Example: Subject is on BNB Chain → also search `agent marketplace NEAR` `agent economy Solana` `agent marketplace Ethereum Base`
   - For non-crypto topics, adapt this to: search for the concept in adjacent ecosystems, markets, or geographies that might have independent solutions

**Why Layer 2 exists**: Layer 1 searches find competitors *within the same category*. Layer 2 searches find competitors *across categories* that serve the same user. The most dangerous competitors are often the ones in a different category — they don't share keywords, don't appear in the same directories, and aren't covered by the same media outlets, but they steal the same customers.

**Anti-tunnel-vision rule**: After completing Layer 1, pause and explicitly write down: (a) the core user problem the subject solves, (b) 2–3 completely different mechanical approaches to that problem, and (c) 2–3 adjacent ecosystems/platforms where solutions might exist. Then run Layer 2 searches targeting those gaps. Do NOT skip Layer 2 even if Layer 1 produced abundant results — abundance in Layer 1 often creates false confidence that the landscape is complete.

For each search, organize findings into the 11-section framework. If a section lacks evidence after initial searches, run additional targeted searches. The research phase is the foundation — a poorly researched document is worse than no document.

**Important**: Always gather data from multiple sources. When analyst firms disagree on market size, present the range rather than cherry-picking one number. Note the date of every data point you use.

### Phase 2: Document Generation

Generate a single Markdown document containing all 11 sections, then deliver it in whatever way your platform supports best:

- **If you can create downloadable files** (e.g., Code Interpreter, computer-use environments, file output tools): save as a `.md` file and provide a download link
- **If you can render rich content inline** (e.g., artifacts, canvas, or similar): present as a rendered document the user can view and copy
- **Otherwise**: output the full Markdown directly in the conversation — the user can copy/paste it into their preferred tool

**When in doubt**: Output the full Markdown in the conversation. It always works.

**Formatting conventions for the Markdown output:**
- Use `#` for the document title, `##` for section headings (numbered), `###` for subsections
- Use Markdown tables (`| Column | Column |`) for all data displays — competitive matrices, scorecards, metrics, opportunity breakdowns
- Use `>` blockquote for the thesis statement (makes it visually prominent)
- Use **bold** for key metrics and player names on first mention
- Use `🟢` `🟡` `🔴` emoji indicators in the Validation Scorecard for Strong/Moderate/Weak signals
- Include a horizontal rule (`---`) between major sections for visual separation
- Cite sources inline using numbered references: `[1]`, `[2]`, etc., with full URLs in Section 11

---

## Required Document Sections (All 11 Mandatory)

Every narrative research document must include all of the following sections, in this order. Each section has a specific purpose and evidence standard.

### Section 1: Narrative Thesis Statement
- **Purpose**: Frame the entire research around a clear, falsifiable hypothesis
- **Format**: A blockquote containing 1–2 sentences stating the hypothesis, followed by 2–3 supporting beliefs
- **Evidence standard**: The thesis should be specific enough to be proven wrong. "AI is growing" is bad. "Personal AI agents are transitioning from developer tools to mainstream consumer products, as evidenced by [specific signal]" is good.
- **Why this matters**: Without a clear thesis, the research becomes a survey rather than a validation exercise. The thesis gives every subsequent section a job: support it, challenge it, or refine it.

**Example format:**
```markdown
> **Thesis**: Prediction markets are transitioning from niche speculation to a foundational
> layer of global information infrastructure — what Vitalik Buterin calls "info finance."
> The 2024 U.S. election was the catalyst, but 130x volume growth, $44B in 2025 trading
> volume, and entry of Robinhood, DraftKings, and ICE signal a structural shift, not a cycle.

**Supporting beliefs:**
1. The accuracy gap between prediction markets and traditional polling has created permanent credibility
2. Regulatory momentum (CFTC favorable posture, federal court rulings) has crossed a tipping point
3. Distribution through mainstream fintech platforms eliminates the cold-start problem
```

### Section 2: Why Now? — Catalyst Analysis
- **Purpose**: Identify the specific forces making this trend possible *now* rather than 5 years ago
- **Subsections**: Technology enablers, cost curve changes, behavioral shifts, infrastructure readiness, regulatory changes
- **Evidence standard**: Each catalyst should reference specific, dated events or data points (not vague trends)
- **Why this matters**: If you can't answer "why now" convincingly, the narrative may be premature. This is the most important differentiator between real trends and hype.

### Section 3: Market Sizing & Growth Trajectory
- **Purpose**: Quantify the opportunity with both top-down and bottom-up data
- **Format**: Markdown table with metrics, values, and sources
- **Required data points**: Current market size, growth rate (CAGR), projections (3–5 year and 10-year if available), key growth signals
- **Evidence standard**: Cite specific analyst firms (e.g., "Grand View Research estimates..."). When sources disagree, show the range rather than picking one number.

### Section 4: Demand Validation — Who's Pulling?
- **Purpose**: Prove that real customers (not just investors or media) want this
- **Subsections**: Revealed demand (actual behavior — revenue, users, downloads), stated demand (surveys, sentiment), demand gap (where demand exists but is unmet)
- **Evidence standard**: Prioritize revealed demand (people spending money) over stated demand (people saying they'd spend money). The demand gap analysis is where the best opportunities often hide.

### Section 5: Supply-Side Mapping — Who's Building?
- **Purpose**: Map the competitive landscape with enough detail to identify positioning gaps
- **Format**: Markdown comparison table with key players, model, regulation status, funding/valuation, traction, and key differentiator
- **Subsections**: Competitive dynamics — market structure (fragmented vs. consolidated), strategic tensions (open vs. closed, regulated vs. unregulated), incumbent vs. attacker dynamics
- **Competitor completeness check** (mandatory before finalizing this section): Review the table and ask:
  1. "Are all competitors using the same *type* of approach?" → If yes, you likely missed alternative-approach competitors. Go back to Layer 2 search #7.
  2. "Are all competitors on the same chain / platform / ecosystem?" → If yes, you likely missed cross-ecosystem competitors. Go back to Layer 2 search #8.
  3. "Would a user choosing between these options ever say 'or I could just use [something completely different]'?" → If yes, that "something different" is a missing competitor.
  If any check triggers, run additional searches before proceeding. Note any gaps you couldn't fill in Section 11 (Limitations).

### Section 6: Key Player Operational Deep Dive
- **Purpose**: Go beyond positioning to evaluate how well each major player is actually executing
- **Format**: For each key player (3–5 players), include a Markdown metrics table (revenue, users, growth, valuation, funding) and three paragraphs: **Strengths**, **Weaknesses**, and **Operational Verdict**
- **Close with**: A comparative scorecard table rating all players across 5–7 dimensions using emoji signals (🟢/🟡/🔴)
- **Evidence standard**: Use specific numbers, not vague qualifiers. "$263M in fee revenue, up 994% YoY" not "strong revenue growth."
- **Why this matters**: This section separates narrative research from generic market reports. Most research stops at positioning; operational analysis reveals who's actually winning versus who's just well-funded.

### Section 7: Trend Validation Scorecard
- **Purpose**: Provide a structured, honest assessment of the narrative's strength
- **Format**: Markdown table with 7–8 validation dimensions, each rated 🟢 Strong / 🟡 Moderate / 🔴 Weak with evidence summary
- **Required dimensions**: Technology readiness, customer demand, funding momentum, regulatory environment, unit economics viability, talent migration, incumbent acknowledgment, and a domain-specific trust/integrity dimension
- **Close with**: An overall assessment paragraph summarizing the score and identifying the critical vulnerability
- **Honesty enforcement rule**: The scorecard MUST contain at least one 🟡 or 🔴 rating. An all-🟢 scorecard is almost certainly wrong — every trend has weaknesses. If you cannot find a single dimension to rate below 🟢, you have not researched deeply enough. Go back to Search #4 (risks and criticism) and run additional counter-narrative searches before proceeding. If after additional research every dimension genuinely appears strong, rate the weakest dimension 🟡 and explain in the evidence column why you consider it the relative weak point despite strong overall signals.
- **Why this matters**: This is the intellectual honesty checkpoint. It forces the researcher to acknowledge weaknesses rather than presenting only the bull case. Readers who see an all-🟢 scorecard will (correctly) distrust the entire document.

### Section 8: Risks, Counter-Narratives & Kill Criteria
- **Purpose**: Actively try to *disprove* the thesis
- **Format**: 3–4 specific counter-narratives (each as a subsection with a provocative title), followed by numbered kill criteria
- **Kill criteria**: Specific, observable signals that would indicate the narrative is failing (e.g., "Monthly volume declines below $5B for 3+ consecutive months outside election periods"). These should be concrete enough that you could monitor them.
- **Why this matters**: The best narrative research takes the bear case seriously. Counter-narratives that feel genuinely threatening (not strawmen) make the bull case stronger by acknowledging real risks.

### Section 9: Analogies & Pattern Matching
- **Purpose**: Compare to historical trends that followed similar trajectories
- **Format**: Markdown table with 3–4 patterns, each with columns: Pattern, Similarity, Outcome, and Implication
- **Selection criteria**: Choose analogies that are genuinely instructive (not just flattering). Include at least one analogy where the historical pattern *failed* as a cautionary comparison.

### Section 10: Opportunity Map & Project Ideas
- **Purpose**: Translate validated findings into actionable concepts
- **Format**: 4–5 distinct opportunities, each in a structured Markdown table with: Concept, Evidence (tracing back to specific sections), Target Market, Feasibility, and First Step
- **Evidence standard**: Every opportunity must trace back to specific evidence from the research. "This seems promising" is insufficient — "ClawHub has 5,700 skills but no security vetting (Section 6), and Gartner predicts guardian agents = 10–15% of market (Section 3)" is the standard.

### Section 11: Sources, Data Freshness & Methodology
- **Purpose**: Full transparency on where the data came from
- **Format**: Numbered list of all sources with URLs, grouped by type (primary sources, analyst reports, news/media)
- **Required**: A methodology paragraph explaining the research approach, and an honest limitations paragraph acknowledging data gaps, source disagreements, and research blind spots
- **Citation verification rule**: Before finalizing, re-check every numbered citation in the document. For each `[N]` reference, verify: (a) source [N] actually exists in the Sources section, (b) the claim attributed to source [N] is actually supported by that source, (c) no source URL is fabricated. If you do not have web search, flag this explicitly: *"Sources are based on training knowledge and have not been verified via live web search. URLs may be outdated or inaccurate."* This is critical because LLMs without web search (especially GPT-4, Llama, local models) can hallucinate plausible-looking URLs and source names. The user must know whether citations are verified or best-effort.

---

## Quality Checklist

Before delivering the document, verify every item. Items marked ❗ are **hard requirements** — if they fail, fix before delivering.

- [ ] ❗ All 11 sections are present and populated with real evidence
- [ ] ❗ Thesis is specific and falsifiable (not a vague "X is growing")
- [ ] Market sizing includes at least 3 data points from named analyst sources
- [ ] Key player analysis has specific revenue/user/funding numbers (not just "strong growth")
- [ ] ❗ Validation scorecard has at least one 🟡 or 🔴 rating (all-🟢 = reject and redo Section 7)
- [ ] ❗ Kill criteria are specific and observable (not vague "if things slow down")
- [ ] At least one historical analogy shows a pattern that *failed*
- [ ] Every opportunity in Section 10 traces back to evidence in earlier sections
- [ ] ❗ Every `[N]` citation in the text has a matching entry in Section 11 Sources
- [ ] Sources section includes 10+ cited sources with URLs
- [ ] Limitations paragraph honestly acknowledges gaps
- [ ] ❗ If web search was NOT used, this is stated prominently in Section 11 and a warning about citation reliability is included

---

## Deeper Ideation Mode

Sometimes the standard 4–5 opportunities in Section 10 don't resonate with the user. They might say:
- "These opportunities don't excite me"
- "I want different / more ambitious / more niche ideas"
- "These are too crowded — find me gaps nobody is addressing"
- "None of these fit my skills / resources / interests"
- "Can you go deeper on the opportunity side?"

When this happens, activate **Deeper Ideation Mode** — an extended version of Section 10 that generates a wider, more creative set of product concepts. This mode stays within the narrative-research prompt (no context switch required) and leverages all the evidence already gathered in Sections 1–9.

### How Deeper Ideation Works

**Step 1: Identify the rejection reason.** Ask or infer why the standard opportunities didn't fit:

| Rejection Reason | Ideation Lens |
|-----------------|---------------|
| "Too crowded / obvious" | Focus on **underserved niches** and **contrarian angles** from the counter-narratives (Section 8) |
| "Too ambitious / expensive" | Focus on **low-capital, high-leverage plays** — tools, data products, content, micro-SaaS |
| "Too boring / not technical enough" | Focus on **infrastructure and protocol-level** opportunities from the technical architecture gaps |
| "Doesn't fit my skills" | Ask what the user's strengths are (engineering, design, sales, content, domain expertise) and map opportunities to those strengths |
| "I want something more creative" | Use **pattern-breaking techniques**: invert the thesis, combine two unrelated Sections, apply an analogy from Section 9 literally |

**Step 2: Generate 8–12 opportunity concepts** using the expanded format below. Cast a wider net than Section 10's standard 4–5 — the goal is volume and variety, not just the "obvious" plays.

**Token budget note**: The full 8–12 concepts with expanded format can exceed 3,000 tokens. If you are running on a model with limited output length (GPT-4o: ~4K output tokens, Gemini Flash: ~8K), reduce to 6–8 concepts and use a compact format: one-liner + archetype + feasibility + first step (skip evidence trail, why it's non-obvious, and revenue model). You can always expand individual concepts on user request. If output gets truncated mid-document, stop at a clean concept boundary and tell the user to ask you to continue.

**Step 3: Organize by archetype.** Group opportunities into archetypes so the user can see the landscape:

| Archetype | Description | Example |
|-----------|-------------|---------|
| 🛠️ **Picks & Shovels** | Infrastructure that every player in the space needs | Data APIs, developer tools, indexing services |
| 🛡️ **Trust Layer** | Products that make the space safer or more trustworthy | Risk scoring, insurance, audit marketplaces |
| 🎯 **Vertical Wedge** | A product that owns one narrow use case deeply | Stablecoin-only yield optimizer, DAO treasury management |
| 🌉 **Bridge Product** | Connects the new market to an existing, larger market | Institutional compliance wrapper, white-label for neobanks |
| 📊 **Intelligence Product** | Monetizes data, analysis, or insight from the market | Newsletters, dashboards, research-as-a-service |
| 🔮 **Contrarian Bet** | Built on a counter-narrative from Section 8 — bets the consensus is wrong | Products that profit if the trend fails, hedging tools |

**Step 4: Present using the expanded opportunity format:**

```markdown
### Opportunity [N]: [Name]
- **Archetype**: [Picks & Shovels / Trust Layer / Vertical Wedge / Bridge / Intelligence / Contrarian]
- **One-liner**: [What it does in one sentence]
- **Evidence trail**: [Which specific sections/findings support this — e.g., "Section 4 demand gap + Section 6 Yearn's weakness"]
- **Why it's non-obvious**: [What insight makes this different from the standard ideas]
- **Target user**: [Who specifically]
- **Revenue model**: [How it makes money]
- **Feasibility**: 🟢 High / 🟡 Medium / 🔴 Low
- **First step**: [One concrete action to test this in 2 weeks]
```

### Deeper Ideation Techniques

When generating the expanded set, use these techniques to find non-obvious opportunities:

1. **Invert the thesis**: If the thesis says "X is growing," ask "who profits if X fails?" or "what happens to the losers?" — there's often a product in serving the disrupted.
2. **Follow the friction**: Re-read Sections 4 (demand gap) and 6 (player weaknesses) specifically looking for complaints, unmet needs, and workarounds. Every workaround is a product opportunity.
3. **Cross-pollinate from Section 9**: Take a historical analogy and ask "what product category emerged from that analogous trend?" — then check if it exists in the current market.
4. **Stack two weaknesses**: Find two different players with complementary weaknesses (Section 6) and design a product that exploits both simultaneously.
5. **Serve the builders**: Every growing market creates demand for developer tools, SDKs, testing infrastructure, and monitoring. These "picks and shovels" are often lower-risk than the end-user products.
6. **Shrink the scope radically**: Take any Section 10 opportunity and ask "what's the smallest, cheapest version of this I could ship in 2 weeks?" — that micro-version is often a viable product itself.

### Companion Prompt: Business Idea Plan

After the user selects their preferred opportunities from Deeper Ideation Mode, suggest they develop them further with this exact message: *"Want me to turn [selected opportunity name] into a full product definition? I can build out: target user persona, value proposition, MVP features, technical architecture, business model, go-to-market strategy, competitive moat, risk analysis, and a 90-day build plan."*

If the user has the **Business Idea Plan** prompt (a companion 12-dimension product definition framework), use it — it produces a structured Markdown document with all 12 dimensions. If you don't have it, produce a product plan following this structure: problem → target user (with persona) → value proposition → MVP features (5 max) → technical architecture → business model (pricing + unit economics) → go-to-market (3 phases) → moat → top 3 risks with mitigations → 90-day plan with weekly milestones.

---

## Known Limitations

This prompt's outputs should be understood within the following constraints:

1. **Data freshness**: Research relies on web search results available at the time of generation. Markets move fast — data points may be days to weeks old. Users should verify critical numbers (revenue, valuations, user counts) against primary sources before using in high-stakes decisions.

2. **Source reliability**: Not all web sources are equally trustworthy. The prompt prioritizes analyst reports, company disclosures, and reputable media, but cannot fully verify every claim. Single-source data points should be treated with extra skepticism.

3. **AI interpretation risk**: Market narratives involve judgment calls — what counts as a "strong" signal vs. "moderate" is inherently subjective. The validation scorecard provides structure but not certainty. Users should treat ratings as a starting point for discussion, not definitive assessments.

4. **Survivorship bias**: Web search results tend to surface companies that are well-funded and well-covered. Stealth-mode startups, emerging players in non-English markets, and open-source projects with low media coverage may be underrepresented in the competitive analysis.

5. **No financial advice**: This prompt produces research and analysis, not investment recommendations. The opportunity map identifies areas worth exploring — it does not constitute advice to invest money, allocate resources, or make business decisions without further due diligence.

6. **Temporal context**: Regulatory environments, competitive landscapes, and market sizes can shift rapidly. A document generated today may not reflect conditions a month from now. Treat each output as a point-in-time snapshot, not a permanent assessment.

7. **Web search availability**: This prompt works best with web search enabled. Without it, the AI will use its training knowledge (which has a cutoff date) and the output will be less current. The document should note prominently if web search was not available during generation.

8. **LLM capability variance**: Different models handle web search, long-form output, and Markdown rendering differently. If a model truncates the output, ask it to continue from where it stopped. If tables render poorly, ask for a simplified format. The 11-section structure is designed to work within typical context window limits, but very large research topics may require the AI to be more concise in some sections.

9. **Cross-category competitor blind spots**: The most dangerous research gap is missing competitors that solve the same user problem with completely different mechanics. Web search tends to cluster results by category (e.g., "bonding curve platforms" or "SocialFi protocols"), which means competitors in adjacent categories (e.g., "escrow-based agent marketplaces") may not appear. The Layer 2 search strategy and Section 5 completeness check are designed to mitigate this, but cannot fully eliminate it — especially for very new or poorly-documented projects. If a user identifies a missing competitor, treat it as a signal to re-examine the search methodology, not just add the competitor to the table.

---

## Example Prompts

Use any of these after providing this document as context:

- "Research the prediction market trend for me"
- "I want to understand if the personal AI agent space is real or hype"
- "Do a structured deep dive on the autonomous vehicle market"
- "Help me validate whether prediction markets are a good opportunity"
- "Create a market research report on the rise of AI coding agents"
- "Is the spatial computing / AR market ready for mainstream?"
- "Analyze the competitive landscape of AI-powered education platforms"
- "my boss wants a report on whether we should invest in agentic AI — needs real data"
- "These opportunities don't excite me — give me more creative ideas" *(triggers Deeper Ideation Mode)*
- "I want more niche, less obvious product ideas from this research" *(triggers Deeper Ideation Mode)*
- "None of these fit my skills — I'm a backend engineer, what should I build?" *(triggers Deeper Ideation Mode)*

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| v1.0 | Feb 2026 | Initial skill — Word (.docx) output, Claude-only |
| v2.0 | Feb 2026 | Switched to Markdown output, zero dependencies, added Known Limitations |
| v2.1 | Feb 2026 | Added Deeper Ideation Mode (6 archetypes, 6 techniques, 8–12 concepts) |
| v2.2 | Feb 2026 | Platform-adaptive output delivery (artifact / file / inline) |
| v3.0 | Feb 2026 | **LLM-agnostic rewrite** — works with ChatGPT, Gemini, Claude, and any model with web search. Removed Claude-specific YAML frontmatter, artifact references, filesystem paths, and skill-trigger language. Added "How to Use" guide, LLM capability variance note, and changelog. Reframed business-idea-plan as companion prompt rather than skill dependency. |
| v3.1 | Feb 25, 2026 | **Anti-blind-spot patch** — Added Layer 2 search strategy (problem-reframe, alternative-solution, cross-ecosystem searches) to prevent missing competitors that solve the same problem with different mechanics. Added Section 5 competitor completeness check (3 mandatory questions). Added Known Limitation #9 (cross-category blind spots). Minimum search count raised from 5 to 8. Root cause: ClawFriend research missed NEAR AI Agent Market because all searches were anchored to subject's mechanics (bonding curves) rather than the user problem (agents transacting economically). |
| v3.2 | Feb 25, 2026 | **Quality enforcement patch** — (1) Section 7: added hard honesty enforcement rule — all-🟢 scorecard triggers mandatory re-research, weakest dimension must be rated 🟡 minimum. (2) Deeper Ideation: added token budget guidance — compact format fallback for GPT-4o/Gemini Flash output limits. (3) Section 11: added citation verification rule — explicit hallucination warning when web search unavailable. (4) Quality checklist: 6 items upgraded to hard requirements (❗) that block delivery if failed. (5) Companion prompt handoff: specific message template + fallback structure. Source: TeamAgent evaluation rubric (87/100 → targeting 93-95). |
