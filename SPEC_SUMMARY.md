# Narrative Research Skill — Specification Summary

## Skill Identity

| Field | Value |
|-------|-------|
| **Name** | `narrative-research` |
| **Output** | Professional Word document (.docx) |
| **Automation** | Fully automated (web search → document generation) |
| **Required Sections** | All 11 (see below) |
| **Dependencies** | `docx` npm library, `web_search` tool, `docx` skill |

---

## What It Does

This skill produces a **structured narrative research document** — a thesis-driven validation of whether an emerging market trend is real, how large the opportunity is, who the key players are (and how well they're executing), and what actionable opportunities exist.

**Core philosophy**: Start with a falsifiable hypothesis, then systematically gather evidence to support, challenge, or refine it.

---

## Trigger Conditions

The skill activates when the user wants:
- A structured analysis of an emerging trend or market narrative
- Validation of whether a market opportunity is real
- A competitive landscape analysis with operational depth
- An investment thesis or opportunity assessment
- A research report combining market data + competitive analysis + actionable ideas

**Example triggers**:
- "Research the prediction market trend for me"
- "Is the personal AI agent space real or hype?"
- "Do a deep dive on the autonomous vehicle market"
- "Create a market research report on AI coding agents"
- "My boss wants me to present on whether we should invest in agentic AI"

**Does NOT trigger for**: Simple factual questions, news summaries, financial advice, single-company analysis (use general research instead).

---

## Workflow (2 Phases)

### Phase 1: Research
- Minimum 3-5 web searches, typically more for complex topics
- Search strategy: core topic → key players → market size → risks/criticism → per-player operational data
- Organize findings into the 11-section framework before writing

### Phase 2: Document Generation
- Uses `docx` npm library (reads docx SKILL.md first)
- Professional formatting with consistent color palette, tables, headers/footers
- All 11 sections populated with real, cited evidence

---

## The 11 Mandatory Sections

| # | Section | Purpose | Key Deliverable |
|---|---------|---------|-----------------|
| 1 | **Narrative Thesis** | Frame a falsifiable hypothesis | Highlighted thesis box |
| 2 | **Why Now? Catalysts** | What changed to make this possible now | 3-4 specific catalyst forces |
| 3 | **Market Sizing** | Quantify the opportunity | Tables with TAM, CAGR, projections |
| 4 | **Demand Validation** | Prove real customers want this | Revealed vs. stated demand + gap |
| 5 | **Supply-Side Map** | Map the competitive landscape | Player comparison table |
| 6 | **Key Player Deep Dive** | Evaluate operational execution | Per-player metrics + Strengths/Weaknesses/Verdict + Comparative Scorecard |
| 7 | **Validation Scorecard** | Honest assessment of narrative strength | 7-8 dimensions rated Strong/Moderate/Weak |
| 8 | **Risks & Counter-Narratives** | Actively try to disprove the thesis | 3-4 counter-narratives + kill criteria |
| 9 | **Analogies** | Historical pattern matching | 3-4 comparisons (including a failure) |
| 10 | **Opportunity Map** | Actionable project ideas | 4-5 opportunities with evidence + first steps |
| 11 | **Sources & Methodology** | Full transparency | 10+ sources + honest limitations |

---

## Design Specifications

### Color Palette
- Dark Navy `#1B2A4A` — H1 headings, table headers
- Accent Blue `#2E75B6` — H2 headings, decorative elements, dividers
- Light Blue `#D5E8F0` — Thesis box, opportunity table labels
- Light Gray `#F2F2F2` — Alternating table rows
- Signal Green `#27AE60` — "Strong" ratings
- Signal Amber `#E67E22` — "Moderate" ratings
- Signal Red `#C0392B` — "Weak" ratings

### Document Structure
- **Cover page**: Title, subtitle, date, confidentiality notice
- **Headers**: Right-aligned "Narrative Research: [Topic] | [Month Year]"
- **Footers**: Centered page numbers
- **Section breaks**: Blue divider lines after each H1
- **Tables**: Alternating rows, dark headers, DXA widths, cell padding

---

## Quality Checklist (Built Into Skill)

Before delivering, the skill verifies:
- ✅ All 11 sections present and populated
- ✅ Thesis is specific and falsifiable
- ✅ Market sizing includes 3+ data points from named sources
- ✅ Key player analysis has specific numbers (not just "strong growth")
- ✅ Validation scorecard has at least one non-Strong rating
- ✅ Kill criteria are specific and observable
- ✅ At least one historical failure analogy included
- ✅ Every opportunity traces to research evidence
- ✅ 10+ cited sources
- ✅ Honest limitations paragraph

---

## Test Cases

### Test 1: Prediction Markets
**Prompt**: Research whether prediction markets are a real trend or election-year hype
**Expected**: Full 11-section doc with $44B volume data, Kalshi/Polymarket/Robinhood deep dives, regulatory risk analysis

### Test 2: AI Coding Agents
**Prompt**: Research the AI coding agents market (Claude Code, Cursor, Copilot, Devin)
**Expected**: Doc with thesis on standalone agents vs. IDE features, market sizing, 5+ player comparison, opportunity map

### Test 3: Agentic AI (Executive Presentation)
**Prompt**: Put together a research doc on agentic AI for executive presentation
**Expected**: Polished doc with $8-12B market data, named analyst sources, clear risks, professional formatting

---

## File Structure

```
narrative-research/
├── SKILL.md              # Main skill instructions (required)
└── evals/
    └── evals.json        # Test cases for validation
```

---

## Future Enhancements (Not In V1)

- **Template scripts**: Pre-built .js templates for common document patterns (could reduce generation time)
- **Sector-specific references**: Pre-loaded context for frequently researched sectors (AI, fintech, healthcare, crypto)
- **Multi-format output**: PowerPoint summary deck alongside the Word document
- **Data freshness tracking**: Automated flagging when cited data points are older than 3 months
- **Comparison mode**: Side-by-side narrative comparison of two competing trends
