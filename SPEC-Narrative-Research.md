# Narrative Research Skill — Specification Summary (v2)

## Changes from v1
- ~~Word document (.docx)~~ → **Markdown (.md)** output
- ~~docx npm library dependency~~ → **Zero dependencies** — works in Claude.ai, Claude Projects, Claude Code, any environment
- **Added**: Known Limitations section (7 items) — addresses BGK questions on data freshness, source reliability, AI interpretation risk, survivorship bias, financial advice disclaimer, temporal context, and search availability fallback
- All 11 sections, quality checklist, and research methodology unchanged

---

## Skill Identity

| Field | Value |
|-------|-------|
| **Name** | `narrative-research` |
| **Output** | Markdown (.md) |
| **Dependencies** | None (web search recommended but not required) |
| **Required Sections** | All 11 |
| **Automation** | Fully automated — web search → Markdown generation |

---

## What It Does

Produces a **thesis-driven narrative research document** that validates whether an emerging market trend is real, quantifies the opportunity, maps who's building and how well they're executing, and identifies actionable opportunities — all in a single structured Markdown file.

**Core philosophy**: Start with a falsifiable hypothesis, then systematically gather evidence to support, challenge, or refine it.

---

## Trigger Conditions

**Activates when** the user wants:
- A structured analysis of an emerging trend or narrative
- Validation of whether a market opportunity is real
- A competitive landscape with operational depth
- An investment thesis or opportunity assessment
- A research report combining market data + competitive analysis + actionable ideas

**Example triggers**:
- "Research the prediction market trend for me"
- "Is the personal AI agent space real or hype?"
- "Do a deep dive on the autonomous vehicle market"
- "my boss wants a report on whether we should invest in agentic AI"

**Does NOT trigger for**: Simple factual questions, news summaries, financial advice, single-company analysis.

---

## Workflow

### Phase 1: Research (5–10 web searches)
1. Core topic → market size → key players → risks → per-player operational data
2. Organize findings into the 11-section framework
3. Run additional searches if any section lacks evidence

### Phase 2: Markdown Generation
- Single .md file with all 11 sections
- Tables, blockquotes, emoji indicators (🟢🟡🔴), horizontal rules
- Inline citations → full source list in Section 11
- Save to `/mnt/user-data/outputs/` and present

---

## The 11 Mandatory Sections

| # | Section | Purpose | Key Deliverable |
|---|---------|---------|-----------------|
| 1 | **Narrative Thesis** | Falsifiable hypothesis | Blockquote thesis + supporting beliefs |
| 2 | **Why Now? Catalysts** | What changed to make this possible now | 3–4 dated catalyst forces |
| 3 | **Market Sizing** | Quantify the opportunity | Table with TAM, CAGR, projections, sources |
| 4 | **Demand Validation** | Prove real customers want this | Revealed vs. stated demand + gap |
| 5 | **Supply-Side Map** | Competitive landscape | Player comparison table |
| 6 | **Key Player Deep Dive** | Operational execution analysis | Per-player metrics + S/W/Verdict + Scorecard |
| 7 | **Validation Scorecard** | Honest signal assessment | 7–8 dimensions rated 🟢/🟡/🔴 |
| 8 | **Risks & Counter-Narratives** | Actively disprove the thesis | 3–4 counter-narratives + kill criteria |
| 9 | **Analogies** | Historical pattern matching | 3–4 comparisons (including a failure) |
| 10 | **Opportunity Map** | Actionable project ideas | 4–5 opportunities with evidence + first steps |
| 11 | **Sources & Methodology** | Full transparency | 10+ sources + limitations paragraph |

---

## Markdown Formatting Conventions

| Element | Markdown Syntax | Usage |
|---------|----------------|-------|
| Document title | `#` | One per document |
| Section headings | `## 1. Section Name` | All 11 sections |
| Subsections | `### Subsection` | Within sections |
| Thesis statement | `> **Thesis**: ...` | Section 1 blockquote |
| Data tables | `\| Col \| Col \|` | Sizing, scorecard, players, opportunities |
| Signal ratings | 🟢 🟡 🔴 | Validation scorecard, comparative scorecard |
| Section dividers | `---` | Between major sections |
| Inline citations | `[1]`, `[2]` | Throughout, resolved in Section 11 |
| Key metrics | `**$263M**` | Bold on first mention |

---

## Quality Checklist

- [ ] All 11 sections present with real evidence
- [ ] Thesis is specific and falsifiable
- [ ] Market sizing: 3+ data points from named sources
- [ ] Key players: specific numbers (not "strong growth")
- [ ] Scorecard: at least one 🟡 or 🔴 (all-🟢 = dishonest)
- [ ] Kill criteria: specific and observable
- [ ] At least one failed historical analogy
- [ ] Every opportunity traces to research evidence
- [ ] 10+ cited sources with URLs
- [ ] Honest limitations paragraph

---

## Known Limitations (NEW in v2)

| # | Limitation | Mitigation |
|---|-----------|------------|
| 1 | **Data freshness** — search results may be days/weeks old | Users verify critical numbers against primary sources |
| 2 | **Source reliability** — not all web sources equally trustworthy | Skill prioritizes analyst reports & company disclosures |
| 3 | **AI interpretation risk** — signal ratings are subjective | Scorecard is starting point for discussion, not definitive |
| 4 | **Survivorship bias** — stealth/non-English players underrepresented | Acknowledged in methodology section |
| 5 | **No financial advice** — analysis only, not recommendations | Explicit disclaimer in every output |
| 6 | **Temporal context** — snapshot, not permanent assessment | Date stamp on every document |
| 7 | **Search availability** — degraded without web search | Falls back to training knowledge; notes limitation prominently |

---

## Test Cases

### Test 1: Prediction Markets
**Prompt**: "Research whether prediction markets are a real trend or election-year hype"
**Expected**: Full 11-section .md with $44B volume data, Kalshi/Polymarket/Robinhood deep dives, regulatory risk analysis, 4–5 opportunities

### Test 2: AI Coding Agents
**Prompt**: "Research the AI coding agents market — Claude Code, Cursor, Copilot, Devin"
**Expected**: .md with thesis on standalone agents vs. IDE features, market sizing, 5+ player comparison, opportunity map

### Test 3: Agentic AI (Executive Use Case)
**Prompt**: "my boss wants a report on whether we should invest in agentic AI — needs real data"
**Expected**: Professional .md with $8–12B market data, named analyst sources, clear risks, all 11 sections

---

## File Structure

```
narrative-research/
├── SKILL.md              # Main skill instructions
├── SPEC_SUMMARY.md       # This file — human-readable spec overview
└── evals/
    └── evals.json        # Test cases for validation
```

**No scripts/, references/, or assets/ directories needed** — the skill is self-contained in SKILL.md with zero external dependencies.

---

## Future Enhancements (Not In v1/v2)

- **Sector-specific references**: Pre-loaded context for frequently researched sectors
- **Multi-format output**: Optional .docx or .pptx generation (when environment supports it)
- **Comparison mode**: Side-by-side narrative comparison of two competing trends
- **Auto-refresh**: Re-run research on an existing document to update stale data points
- **Confidence scoring**: Quantitative confidence levels on each section based on source count and agreement
