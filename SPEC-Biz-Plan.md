# Business Idea Plan Skill — Specification Summary

## Skill Identity

| Field | Value |
|-------|-------|
| **Name** | `business-idea-plan` |
| **Output** | Markdown (.md) |
| **Dependencies** | None (web search optional for grounding) |
| **Core Framework** | 12-Dimension Product Definition |
| **Companion Skill** | `narrative-research` (upstream: "Is this market real?") |

---

## What It Does

Transforms a business idea — from vague concept to specific plan — using a **12-dimension framework** that covers every question a product needs to answer before building begins. Each dimension targets a specific failure mode: products fail when they solve imagined problems (Dim 2), target nobody in particular (Dim 4), can't explain their value (Dim 5), overscope the MVP (Dim 6), have no business model (Dim 8), have no distribution plan (Dim 9), or have no moat (Dim 10).

---

## The 12 Dimensions

| # | Dimension | Question It Answers | Failure It Prevents |
|---|-----------|-------------------|-------------------|
| 1 | **Product Name & Tagline** | What is it, in one breath? | Can't explain what you're building |
| 2 | **Problem Statement** | What specific pain exists today? | Solving an imagined problem |
| 3 | **Evidence From Research** | What data validates this pain? | Building without proof of demand |
| 4 | **Target User Persona** | Who exactly is the first user? | Building for "everyone" (= nobody) |
| 5 | **Value Proposition** | Why would they switch? | Marginal improvement nobody adopts |
| 6 | **Core Feature Set (MVP)** | What are the 3–5 features in v1? | Feature creep / over-building |
| 7 | **Technical Architecture** | How does it work under the hood? | Requires nonexistent technology |
| 8 | **Business Model & Unit Economics** | How does it make money? | No path to revenue |
| 9 | **Go-To-Market Strategy** | How do the first 1,000 users find it? | Distribution failure |
| 10 | **Competitive Moat** | What makes this defensible? | Competitors copy and outspend |
| 11 | **Key Risks & Mitigations** | What kills this, how to prevent? | Unacknowledged fatal flaw |
| 12 | **90-Day Build Plan** | What happens weeks 1–12? | No action plan, just a document |

---

## Workflow

```
User Input                       Phase                Output
─────────────                    ─────                ──────
Specific idea ──────────────→  Phase 3: Write  ───→  Full 12-dim plan
Domain, no idea ────→  Quick Ideation (3–5 concepts) → User picks → Phase 3
Vague / unclear ────→  Clarifying questions → Phase 1 → Phase 2/3
From narrative-research ──→  Phase 3 (evidence pre-loaded) → Full plan(s) + comparison
```

---

## Trigger Conditions

**Activates when** the user wants to:
- Define, structure, or evaluate a product idea
- Go from "I want to build X" to a concrete plan
- Compare multiple ideas to choose which to build first
- Turn narrative research findings into buildable products

**Example triggers**:
- "Help me plan a product around DeFi risk scoring"
- "I want to build a robo-advisor for crypto — define the product"
- "Evaluate these 3 business ideas"
- "Turn the opportunity map from my research into product specs"

**Does NOT trigger for**: Market research (use `narrative-research`), pitch decks, financial modeling, legal advice.

---

## Quality Checklist

- [ ] All 12 dimensions populated
- [ ] Problem is real and specific (not hypothetical)
- [ ] 3+ evidence data points with numbers/sources
- [ ] Persona is findable on LinkedIn
- [ ] Value prop is a step-change (10x, not 1.1x)
- [ ] MVP has 3–5 features max
- [ ] Business model shows break-even path
- [ ] GTM has executable Phase 1 tactics
- [ ] At least one 🔴 Critical risk
- [ ] 90-day plan uses nouns (deliverables), not verbs (activities)
- [ ] If multiple products: comparison matrix + build sequence

---

## Multi-Product Mode

When the user provides multiple ideas (or when generating from narrative research), the output includes:

1. **Individual 12-dimension plans** for each product
2. **Comparison Matrix** — table across: category, user, revenue model, Year 1 target, complexity, risk, time to revenue
3. **Recommended Build Sequence** — ordered by speed to revenue, risk, and how earlier products de-risk later ones

---

## Known Limitations

| # | Limitation | Context |
|---|-----------|---------|
| 1 | Revenue estimates are directional | Validate with customer conversations |
| 2 | Architecture is conceptual | Not a full engineering spec |
| 3 | Competitor landscape may be incomplete | Stealth startups may be missed |
| 4 | Persona is illustrative | Validate with discovery interviews |
| 5 | No financial advice | Feasibility testing, not forecasts |
| 6 | 90-day plan assumes 2–5 person team | Adjust for team size |
| 7 | Output quality depends on input specificity | Vague idea → less actionable plan |

---

## Relationship to Other Skills

```
narrative-research          business-idea-plan
"Is this market real?"  →   "What exactly should I build?"
                        →   Uses evidence from Sections 3, 4, 6, 10
                        →   Converts opportunity map into product specs
```

The two skills are independent but complementary. For highest quality:
1. Run `narrative-research` first to validate the market
2. Use the findings (especially Sections 4 Demand Gap, 6 Player Weaknesses, 10 Opportunities) as input to `business-idea-plan`

---

## Test Cases

### Test 1: Specific Idea
**Prompt**: "I want to build a risk scoring API for DeFi protocols. Help me define the product."
**Expected**: Single 12-dimension plan with specific DeFi risk scoring features, B2B API pricing, technical architecture, and 90-day build plan.

### Test 2: Domain Without Specific Idea
**Prompt**: "I want to build something in the prediction market space. What should I build?"
**Expected**: Quick Ideation (3–5 concepts) → user selects → full 12-dimension plan for selected concept(s).

### Test 3: Multiple Ideas From Research
**Prompt**: "Based on the autonomous yield farming research, turn the top 3 opportunities into detailed product plans and tell me which to build first."
**Expected**: Three 12-dimension plans + comparison matrix + recommended build sequence.

### Test 4: Vague / Non-Technical
**Prompt**: "i have an idea for an app that helps people save money using crypto, its kinda like a savings account but better. can you help me plan it?"
**Expected**: Clarifying questions first, then a 12-dimension plan with architecture calibrated for non-technical founder.

---

## File Structure

```
business-idea-plan/
├── SKILL.md              # Main skill instructions
├── SPEC-Biz-Plan.md       # This file
└── evals/
    └── evals.json        # Test cases
```

No scripts, references, or assets needed — fully self-contained.
