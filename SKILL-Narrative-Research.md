---
name: narrative-research
description: "Use this skill whenever the user wants to research, validate, or analyze an emerging market trend, narrative, or investment thesis. Triggers include: requests to 'research a market', 'validate a narrative', 'analyze a trend', 'write a market research report', 'do a deep dive on [industry/trend]', 'is this trend real?', 'should I invest/build in [space]?', or any request that combines market sizing, competitive analysis, and opportunity identification into a structured deliverable. Also triggers when the user names a specific trend or company and wants a structured assessment (e.g., 'research prediction markets', 'analyze the AI agent space', 'what's happening with [company/sector]?'). ALSO triggers when the user is unsatisfied with initial product opportunities and wants deeper, more creative, or more niche ideas — phrases like 'these ideas don't excite me', 'give me more creative opportunities', 'I want non-obvious ideas', or 'none of these fit my skills' activate the Deeper Ideation Mode within this skill. The output is always a structured Markdown document (.md) with a thesis-driven validation framework. This skill should be used even when the user doesn't explicitly say 'narrative research' — if they want a structured, evidence-based analysis of whether a market trend is real and what the opportunities are, this is the right skill. Do NOT use for simple factual questions, news summaries, or financial advice."
---

# Narrative Research Skill (v2.2)

## Overview

This skill produces a **structured narrative research document** — a Markdown file (.md) that validates whether an emerging market trend is real, how large the opportunity is, who the key players are, and what actionable opportunities exist.

The core philosophy is **thesis-driven validation**: start with a falsifiable hypothesis about a market trend, then systematically gather evidence to support, challenge, or refine it. This is different from generic market research (which surveys a market) or due diligence (which evaluates a specific company). Narrative research sits at the intersection — it evaluates a *story about where a market is going* and pressure-tests it with data.

**Output format**: Markdown (.md) — portable, renders natively in Claude.ai artifacts, GitHub, Notion, and any Markdown viewer. No external libraries or dependencies required.

## When This Skill Activates

This skill should be used when the user wants any of the following:
- A structured analysis of an emerging trend or market narrative
- Validation of whether a market opportunity is real
- A competitive landscape analysis with operational depth
- An investment thesis or opportunity assessment
- A research report that combines market data, competitive analysis, and actionable ideas

## Workflow

### Phase 1: Research (5–10 web searches minimum)

Before writing anything, conduct thorough web research on the topic. The goal is to gather enough data to populate all 11 sections with real, cited evidence.

**Search strategy — use at least 5 searches, often 8–10 for complex topics:**

1. **Core topic search**: `[topic] market growth 2025 2026` — gets market size, growth data, recent developments
2. **Key players search**: `[topic] companies funding valuation revenue` — gets competitive landscape data
3. **Market size search**: `[topic] market size TAM forecast billion` — gets analyst projections
4. **Risks and criticism**: `[topic] risks criticism challenges regulation concerns` — gets counter-narratives
5. **Per-player operational data** (repeat for each major player): `[company] revenue users metrics 2025` — gets granular execution data

For each search, mentally organize findings into the 11-section framework. If a section lacks evidence after initial searches, run additional targeted searches. The research phase is the foundation — a poorly researched document is worse than no document.

**Important**: Always gather data from multiple sources. When analyst firms disagree on market size, present the range rather than cherry-picking one number. Note the date of every data point you use.

### Phase 2: Document Generation

Generate a single Markdown file (.md) containing all 11 sections, then deliver it using the appropriate method for the current environment.

**Output delivery — adapt to the runtime environment:**

| Environment | How to detect | Delivery method |
|------------|---------------|-----------------|
| **Claude.ai / Claude app** (web or mobile chat) | No filesystem access, or the user is chatting in claude.ai | Present the full Markdown document as an **artifact** in the conversation. The user can view, copy, or download it directly. |
| **Claude Code / computer-use environment** | Filesystem is available (e.g., `/mnt/user-data/outputs/` exists, or the user has a working directory) | Save the .md file to the appropriate output directory (e.g., `/mnt/user-data/outputs/`) and present the file to the user. |
| **API / other platforms** | Neither of the above applies | Return the full Markdown content in the response. Let the calling application handle display and storage. |

**When in doubt**: If you're unsure which environment you're in, present the document as an artifact — it works everywhere and the user can always save it themselves.

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
- **Why this matters**: This is the intellectual honesty checkpoint. It forces the researcher to acknowledge weaknesses rather than presenting only the bull case.

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

---

## Quality Checklist

Before delivering the document, verify:
- [ ] All 11 sections are present and populated with real evidence
- [ ] Thesis is specific and falsifiable (not a vague "X is growing")
- [ ] Market sizing includes at least 3 data points from named analyst sources
- [ ] Key player analysis has specific revenue/user/funding numbers (not just "strong growth")
- [ ] Validation scorecard has at least one 🟡 or 🔴 rating (all-🟢 is a red flag for intellectual dishonesty)
- [ ] Kill criteria are specific and observable (not vague "if things slow down")
- [ ] At least one historical analogy shows a pattern that *failed*
- [ ] Every opportunity in Section 10 traces back to evidence in earlier sections
- [ ] Sources section includes 10+ cited sources with URLs
- [ ] Limitations paragraph honestly acknowledges gaps

---

## Deeper Ideation Mode

Sometimes the standard 4–5 opportunities in Section 10 don't resonate with the user. They might say:
- "These opportunities don't excite me"
- "I want different / more ambitious / more niche ideas"
- "These are too crowded — find me gaps nobody is addressing"
- "None of these fit my skills / resources / interests"
- "Can you go deeper on the opportunity side?"

When this happens, activate **Deeper Ideation Mode** — an extended version of Section 10 that generates a wider, more creative set of product concepts. This mode stays within the narrative-research skill (no handoff required) and leverages all the evidence already gathered in Sections 1–9.

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

### When to Suggest business-idea-plan

After the user selects their preferred opportunities from Deeper Ideation Mode, suggest they develop them further using the **business-idea-plan** skill's 12-dimension framework: "Want me to turn these into full product definitions with architecture, business model, GTM, and a 90-day build plan?" This creates a natural handoff without requiring the user to know the skill exists.

---

## Known Limitations

This skill's outputs should be understood within the following constraints:

1. **Data freshness**: Research relies on web search results available at the time of generation. Markets move fast — data points may be days to weeks old. Users should verify critical numbers (revenue, valuations, user counts) against primary sources before using in high-stakes decisions.

2. **Source reliability**: Not all web sources are equally trustworthy. The skill prioritizes analyst reports, company disclosures, and reputable media, but cannot fully verify every claim. Single-source data points should be treated with extra skepticism.

3. **AI interpretation risk**: Market narratives involve judgment calls — what counts as a "strong" signal vs. "moderate" is inherently subjective. The validation scorecard provides structure but not certainty. Users should treat ratings as a starting point for discussion, not definitive assessments.

4. **Survivorship bias**: Web search results tend to surface companies that are well-funded and well-covered. Stealth-mode startups, emerging players in non-English markets, and open-source projects with low media coverage may be underrepresented in the competitive analysis.

5. **No financial advice**: This skill produces research and analysis, not investment recommendations. The opportunity map identifies areas worth exploring — it does not constitute advice to invest money, allocate resources, or make business decisions without further due diligence.

6. **Temporal context**: Regulatory environments, competitive landscapes, and market sizes can shift rapidly. A document generated today may not reflect conditions a month from now. Treat each output as a point-in-time snapshot, not a permanent assessment.

7. **Search availability**: The skill requires web search access to function at full capability. If web search is unavailable, the skill can still generate the document structure and populate it with information from its training knowledge, but data freshness and specificity will be significantly reduced. The output will note this limitation prominently.

---

## Example Prompts This Skill Handles

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
