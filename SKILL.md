---
name: narrative-research
description: "Use this skill whenever the user wants to research, validate, or analyze an emerging market trend, narrative, or investment thesis. Triggers include: requests to 'research a market', 'validate a narrative', 'analyze a trend', 'write a market research report', 'do a deep dive on [industry/trend]', 'is this trend real?', 'should I invest/build in [space]?', or any request that combines market sizing, competitive analysis, and opportunity identification into a structured deliverable. Also triggers when the user names a specific trend or company and wants a structured assessment (e.g., 'research prediction markets', 'analyze the AI agent space', 'what's happening with [company/sector]?'). The output is always a professional Word document (.docx) with a thesis-driven validation framework. This skill should be used even when the user doesn't explicitly say 'narrative research' — if they want a structured, evidence-based analysis of whether a market trend is real and what the opportunities are, this is the right skill. Do NOT use for simple factual questions, news summaries, or financial advice."
---

# Narrative Research Skill

## Overview

This skill produces a **structured narrative research document** — a professional Word document (.docx) that validates whether an emerging market trend is real, how large the opportunity is, who the key players are, and what actionable opportunities exist.

The core philosophy is **thesis-driven validation**: start with a falsifiable hypothesis about a market trend, then systematically gather evidence to support, challenge, or refine it. This is different from generic market research (which surveys a market) or due diligence (which evaluates a specific company). Narrative research sits at the intersection — it evaluates a *story about where a market is going* and pressure-tests it with data.

## When This Skill Activates

This skill should be used when the user wants any of the following:
- A structured analysis of an emerging trend or market narrative
- Validation of whether a market opportunity is real
- A competitive landscape analysis with operational depth
- An investment thesis or opportunity assessment
- A research report that combines market data, competitive analysis, and actionable ideas

## Workflow

### Phase 1: Research (3-5 web searches minimum)

Before writing anything, conduct thorough web research on the topic. The goal is to gather enough data to populate all 11 sections with real, cited evidence.

**Search strategy — use at least 3-5 searches, typically more for complex topics:**

1. **Core topic search**: `[topic] market growth 2025 2026` — gets market size, growth data, recent developments
2. **Key players search**: `[topic] key players companies funding valuation` — gets competitive landscape, funding data, revenue metrics
3. **Market size search**: `[topic] market size forecast billion` — gets TAM/SAM projections from analyst firms
4. **Risks and criticism**: `[topic] risks criticism challenges regulation` — gets counter-narratives, regulatory issues
5. **Operational data** (per key player): `[company name] revenue users metrics 2025 2026` — gets granular player-level data

For each search, extract and mentally organize findings into the 11-section framework. If a section lacks evidence after initial searches, run additional targeted searches. The research phase is the foundation — a poorly researched document is worse than no document.

### Phase 2: Document Generation

Generate a professional Word document (.docx) using the `docx` npm library (follow the docx skill at `/mnt/skills/public/docx/SKILL.md` for technical implementation). Always read the docx SKILL.md before generating.

## Required Document Sections (All 11 Mandatory)

Every narrative research document must include all of the following sections, in this order. Each section has a specific purpose and evidence standard.

### Section 1: Narrative Thesis Statement
- **Purpose**: Frame the entire research around a clear, falsifiable hypothesis
- **Format**: A highlighted thesis box with 1-2 sentences stating what the researcher believes is happening in the market, followed by 2-3 supporting beliefs and a statement of purpose
- **Evidence standard**: The thesis should be specific enough to be proven wrong. "AI is growing" is bad. "Personal AI agents are transitioning from developer tools to mainstream consumer products, as evidenced by [specific signal]" is good.
- **Why this matters**: Without a clear thesis, the research becomes a survey rather than a validation exercise. The thesis gives every subsequent section a job: support it, challenge it, or refine it.

### Section 2: Why Now? — Catalyst Analysis
- **Purpose**: Identify the specific forces making this trend possible *now* rather than 5 years ago
- **Subsections**: Technology enablers, cost curve changes, behavioral shifts, infrastructure readiness, regulatory changes
- **Evidence standard**: Each catalyst should reference specific, dated events or data points (not vague trends)
- **Why this matters**: If you can't answer "why now" convincingly, the narrative may be premature. This section is the most important differentiator between real trends and hype.

### Section 3: Market Sizing & Growth Trajectory
- **Purpose**: Quantify the opportunity with both top-down and bottom-up data
- **Format**: Tables with metrics, values, and sources. Include both current market size and growth projections.
- **Required data points**: Current market size, growth rate (CAGR), projections (3-5 year and 10-year if available), geographic breakdown, and key growth signals
- **Evidence standard**: Cite specific analyst firms (e.g., "Grand View Research estimates..."). When sources disagree, show the range rather than picking one number.

### Section 4: Demand Validation — Who's Pulling?
- **Purpose**: Prove that real customers (not just investors or media) want this
- **Subsections**: Revealed demand (actual behavior — revenue, users, downloads, adoption data), stated demand (surveys, sentiment), and demand gap (where demand exists but is unmet)
- **Evidence standard**: Prioritize revealed demand (people spending money) over stated demand (people saying they'd spend money). The demand gap analysis is where the best opportunities often hide.

### Section 5: Supply-Side Mapping — Who's Building?
- **Purpose**: Map the competitive landscape with enough detail to identify positioning gaps
- **Format**: A comparison table with key players, their model, regulation status, funding/valuation, traction metrics, and key differentiator
- **Subsections**: Competitive dynamics analysis covering market structure (fragmented vs. consolidated), strategic tensions (e.g., open vs. closed, regulated vs. unregulated), and incumbent vs. attacker dynamics

### Section 6: Key Player Operational Deep Dive
- **Purpose**: Go beyond positioning to evaluate how well each major player is actually executing
- **Format**: For each key player (3-5 players), include a metrics table (revenue, users, growth, valuation, funding, employees) and three analytical paragraphs: Strengths, Weaknesses, and Operational Verdict
- **Close with**: A comparative operational scorecard table rating all players across 5-7 dimensions using color-coded signals (green/amber/red)
- **Evidence standard**: Use specific numbers, not vague qualifiers. "$263M in fee revenue, up 994% YoY" is good. "Strong revenue growth" is insufficient.
- **Why this matters**: This section separates narrative research from generic market reports. Most research stops at positioning; operational analysis reveals who's actually winning and who's just well-funded.

### Section 7: Trend Validation Scorecard
- **Purpose**: Provide a structured, honest assessment of the narrative's strength
- **Format**: A table with 7-8 validation dimensions, each rated Strong/Moderate/Weak with supporting evidence
- **Required dimensions**: Technology readiness, customer demand, funding momentum, regulatory environment, unit economics viability, talent migration, incumbent acknowledgment, and a trust/integrity dimension specific to the narrative
- **Close with**: An overall assessment paragraph summarizing the score and identifying the critical vulnerability
- **Why this matters**: This is the intellectual honesty checkpoint. It forces the researcher to acknowledge weaknesses rather than presenting only the bull case.

### Section 8: Risks, Counter-Narratives & Kill Criteria
- **Purpose**: Actively try to *disprove* the thesis
- **Format**: 3-4 specific counter-narratives (each as a subsection with a provocative title), followed by a numbered list of kill criteria
- **Kill criteria**: Specific, observable signals that would indicate the narrative is failing (e.g., "Monthly volume declines below $X for 3+ consecutive months"). These should be concrete enough that you could monitor them.
- **Why this matters**: The best narrative research is the research that takes the bear case seriously. Counter-narratives that feel genuinely threatening (not strawmen) make the bull case stronger by acknowledging real risks.

### Section 9: Analogies & Pattern Matching
- **Purpose**: Compare to historical trends that followed similar trajectories
- **Format**: A table with 3-4 historical patterns, each with columns: Pattern, Similarity, Outcome, and Implication for the current narrative
- **Selection criteria**: Choose analogies that are genuinely instructive (not just flattering). Include at least one analogy where the historical pattern *failed* as a cautionary comparison.

### Section 10: Opportunity Map & Project Ideas
- **Purpose**: Translate validated findings into actionable concepts
- **Format**: 4-5 distinct opportunities, each presented in a structured table with: Concept, Evidence (what from the research supports this), Target Market, Feasibility rating, and First Step (a concrete MVP or validation action)
- **Evidence standard**: Every opportunity must trace back to specific evidence from the research. "This seems promising" is not enough — "ClawHub has 5,700 skills but no security vetting (Section 6), and Gartner predicts guardian agents will capture 10-15% of the market (Section 3)" is the standard.

### Section 11: Sources, Data Freshness & Methodology
- **Purpose**: Full transparency on where the data came from
- **Subsections**: Methodology description, primary sources, secondary sources, market data sources, and limitations
- **Required**: An honest limitations paragraph acknowledging data gaps, source disagreements, and research blind spots

## Document Design Specifications

### Visual Standards
- **Font**: Arial throughout
- **Color palette**: Dark navy (#1B2A4A) for H1 headings, accent blue (#2E75B6) for H2 headings and decorative elements, light blue (#D5E8F0) for highlight boxes, light gray (#F2F2F2) for alternating table rows
- **Page size**: US Letter (12240 x 15840 DXA)
- **Margins**: 1 inch all sides
- **Header**: Right-aligned, italic, containing "Narrative Research: [Topic] | [Month Year]"
- **Footer**: Centered page numbers

### Cover Page
- Include: Document type label ("STRUCTURED NARRATIVE RESEARCH"), main title, subtitle, date, and confidentiality notice
- Use centered alignment with decorative borders

### Section Formatting
- Each major section starts with an H1 heading followed by a blue divider line
- Thesis statement is presented in a highlighted box with blue left border
- Tables use alternating row shading and dark navy header rows with white text
- Validation scorecard uses color-coded text: green (#27AE60) for Strong, amber (#E67E22) for Moderate, red (#C0392B) for Weak
- Opportunity tables use light blue left column for labels

### Tables
- Always use DXA width type (never percentages)
- Always set both columnWidths on the table AND width on each cell
- Use cell margins: top 80, bottom 80, left 120, right 120
- Use ShadingType.CLEAR (never SOLID)

## Quality Checklist

Before delivering the document, verify:
- [ ] All 11 sections are present and populated
- [ ] Thesis is specific and falsifiable
- [ ] Market sizing includes at least 3 data points from named sources
- [ ] Key player analysis includes specific revenue/user/funding numbers (not just "strong growth")
- [ ] Validation scorecard has at least one Weak or Moderate rating (all-Strong is a red flag for intellectual dishonesty)
- [ ] Kill criteria are specific and observable
- [ ] At least one analogy shows a historical failure
- [ ] Every opportunity traces back to evidence from the research
- [ ] Sources section includes 10+ cited sources
- [ ] Limitations paragraph honestly acknowledges gaps

## Example Prompts This Skill Handles

- "Research the prediction market trend for me"
- "I want to understand if the personal AI agent space is real or hype"
- "Do a structured deep dive on the autonomous vehicle market"
- "Help me validate whether prediction markets are a good opportunity"
- "Create a market research report on the rise of AI coding agents"
- "Is the spatial computing / AR market ready for mainstream?"
- "Analyze the competitive landscape of AI-powered education platforms"
