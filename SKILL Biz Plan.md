---
name: business-idea-plan
description: "Use this skill whenever the user wants to define, evaluate, structure, or flesh out a business idea, product concept, or startup plan. Triggers include: 'help me plan this product', 'define this business idea', 'I have an idea for...', 'write a product spec', 'evaluate this startup idea', 'how would I build a business around...', 'give me a product plan for...', 'turn this into a buildable concept', 'create a business plan', 'help me think through this product', or any request where the user has identified a market opportunity and wants to transform it into a structured, actionable product definition. Also triggers when a user says 'I want to build X' and needs help going from vague concept to concrete plan. The output is always a structured Markdown document (.md) using the 12-dimension product definition framework. This skill is the natural next step after market research — it takes validated insights and turns them into buildable product specs. Use this skill even when the user doesn't say 'business plan' explicitly — if they're describing a product they want to create and need structure, this is the right skill. Do NOT use for market research (use narrative-research instead), financial modeling, pitch deck creation, or legal/regulatory advice."
---

# Business Idea Plan Skill

## Overview

This skill produces a **structured product definition document** — a Markdown file (.md) that transforms a business idea into a concrete, buildable plan using a 12-dimension framework. Each dimension answers a specific question that takes the idea from "interesting concept" to "I know exactly what to build, for whom, how to make money, and what to do in the first 90 days."

The core philosophy is **evidence-backed product thinking**: every product decision should trace back to a real problem, a real user, and real market evidence — not speculation or wishful thinking. If the user has previously done narrative research on the market, the product definition should reference that research explicitly. If not, light research may be needed to ground the plan in reality.

**Output format**: Markdown (.md) — portable, renders natively in Claude.ai artifacts, GitHub, Notion, and any Markdown viewer. No external dependencies.

**Relationship to narrative-research skill**: The narrative-research skill answers "Is this market real?" This skill answers "What exactly should I build?" They work well in sequence but are fully independent.

## When This Skill Activates

Use this skill when the user wants to:
- Define a product concept with enough detail to start building
- Evaluate whether a business idea is viable
- Structure a vague idea into an actionable plan
- Create a product spec for a startup or side project
- Compare multiple product ideas to decide which to build first
- Turn market research findings into concrete product concepts

## Workflow

### Phase 1: Understand the Idea

Before writing, make sure you understand what the user wants to build. If the idea is vague, ask clarifying questions to identify:
- What problem does this solve?
- Who has this problem?
- Why does the user believe this is a good idea? (what evidence or intuition?)
- What's the user's context? (solo founder, team, hackathon, corporate innovation, side project)

If the user provides a specific idea ("build a risk scoring API for DeFi agents"), proceed directly to Phase 3. If they provide a domain but no specific idea ("I want to build something in DeFi"), generate 3–5 product concepts using the Quick Ideation Format first, then let the user choose which to develop into a full 12-dimension plan.

### Phase 2: Research (if needed)

If the user hasn't provided market context, conduct 2–3 web searches to ground the plan:
- `[problem domain] market size 2025 2026` — validates the opportunity
- `[problem domain] existing solutions competitors` — accounts for competition
- `[target user] pain points challenges` — confirms the problem is real

This is lighter than the narrative-research skill. The goal is grounding, not exhaustive analysis.

### Phase 3: Write the Product Definition

Generate a Markdown file with the full 12-dimension framework. If the user requested multiple ideas, include all plus a comparison matrix and recommended build sequence.

---

## The 12-Dimension Product Definition Framework

Every product definition includes these 12 dimensions, in this order. Each dimension exists because it answers a question that, if left unanswered, causes products to fail.

### Dimension 1: Product Name & Tagline
- **Answers**: What is this, in one breath?
- **Format**: A memorable name + a one-line tagline that communicates core value
- **Why it matters**: If you can't explain it in one sentence, you don't understand it. The tagline forces clarity and becomes the basis for all positioning.
- **Quality bar**: Passes the "bar test" — a stranger at a bar understands immediately.

### Dimension 2: Problem Statement
- **Answers**: What specific pain exists today?
- **Format**: 3–5 sentences describing the problem concretely — who has it, how often, what they do about it now
- **Why it matters**: Products fail when they solve imagined problems. The statement should describe pain real enough that someone would pay to make it go away.
- **Quality bar**: Could you find 10 people who nod vigorously reading this?

### Dimension 3: Evidence From Research
- **Answers**: What data validates this pain and opportunity?
- **Format**: 4–6 bullet points with specific data — market size, user behavior, competitor traction, trends. Reference narrative research sections if available.
- **Why it matters**: Bridges "I think this is good" to "here's proof." Each bullet should be a fact with a number, a source, or a specific observable behavior — not a vague claim.

### Dimension 4: Target User Persona
- **Answers**: Who exactly is the first user?
- **Format**: A named persona with age, role, context, current behavior, and pain level. Specific enough to represent a real segment.
- **Why it matters**: "Everyone" is not a target user. The persona forces prioritization and shapes every subsequent decision.
- **Quality bar**: Could you find this person on LinkedIn?

### Dimension 5: Value Proposition
- **Answers**: Why would the target user switch from their current solution?
- **Format**: One core sentence, followed by a comparison to alternatives explaining why this is meaningfully better
- **Why it matters**: Users don't switch for marginal improvements. The value prop must articulate a step-change — 10x better, 10x cheaper, or solving something previously impossible.

### Dimension 6: Core Feature Set (MVP)
- **Answers**: What are the 3–5 features in version 1?
- **Format**: Numbered list, each feature in 1–2 sentences. Focus on what makes the product *work*, not what makes it polished.
- **Why it matters**: The MVP is the smallest thing you can build to test whether the value proposition is real. Feature creep kills early-stage products.
- **Quality bar**: For each feature, ask "if I removed this, would the core value still work?" If yes, remove it.

### Dimension 7: Technical Architecture
- **Answers**: How does this work under the hood?
- **Format**: Structured breakdown of major layers (data, logic, distribution) with key tech choices. Use indented hierarchies or ASCII diagrams. Specify enough to estimate build effort.
- **Why it matters**: Ideas meet reality here. A product requiring nonexistent technology is a research project, not a startup.
- **Calibration**: Match depth to user's context — specific frameworks for technical founders, major components for non-technical founders.

### Dimension 8: Business Model & Unit Economics
- **Answers**: How does this make money, and do the numbers work?
- **Format**: Revenue stream table (model + pricing), key unit economics, Year 1 revenue target, break-even point
- **Why it matters**: A product without a business model is a hobby. Numbers don't need to be precise, but they must be plausible at the back-of-envelope level.

### Dimension 9: Go-To-Market Strategy
- **Answers**: How do the first 1,000 users find this?
- **Format**: 3 phases (months 1–3, 3–6, 6–12) with specific, concrete actions and milestones
- **Why it matters**: Most products die from distribution failure, not product failure. GTM should be as specific as the feature set.
- **Quality bar**: Could you execute Phase 1 starting Monday?

### Dimension 10: Competitive Moat
- **Answers**: What makes this defensible over time?
- **Format**: 2–3 moat types (data, network effect, trust, switching cost, regulatory) with how each compounds
- **Why it matters**: Every success attracts competition. The moat doesn't need to exist on day 1 but the plan should show how it develops.
- **Warning**: "We'll execute better" is not a moat.

### Dimension 11: Key Risks & Mitigations
- **Answers**: What kills this, and how do you prevent it?
- **Format**: Table with 3–5 risks rated 🔴 Critical / 🟡 Medium / 🟢 Low, each with a concrete mitigation
- **Why it matters**: Acknowledging risks isn't pessimism — it's preparation. Include at least one 🔴 Critical risk. If there are none, you haven't thought hard enough.

### Dimension 12: 90-Day Build Plan
- **Answers**: What happens in weeks 1–4, 5–8, and 9–12?
- **Format**: Three time blocks with 3–5 concrete deliverables each — shipped features, signed customers, published reports (nouns, not verbs)
- **Why it matters**: Transforms the document into an action plan. Forces sequencing.
- **Quality bar**: Someone reading this knows exactly what "done" looks like at the end of each month.

---

## Quick Ideation Format

When the user provides a domain but not a specific idea, generate 3–5 concepts using this format first:

```markdown
### Idea [N]: [Product Name]
- **One-liner**: [What it does in one sentence]
- **Problem**: [The specific pain it solves]
- **User**: [Who has this problem]
- **Revenue model**: [How it makes money]
- **Why now**: [What makes this possible/urgent today]
- **Feasibility**: 🟢 High / 🟡 Medium / 🔴 Low
```

Present to the user, let them choose, then develop the chosen idea(s) into full 12-dimension plans.

---

## Multi-Product Output

When defining multiple ideas, add two sections after the individual plans:

### Product Comparison Matrix
Table comparing all products across: category, primary user, revenue model, Year 1 target, break-even, technical complexity, regulatory risk, time to first revenue, market timing.

### Recommended Build Sequence
Ordered list with rationale. Consider: speed to revenue, risk level, and how earlier products create infrastructure or de-risk later ones. Products that compose into a stack (each feeding the next) should be called out explicitly.

---

## Formatting Conventions

- `#` for document title, `##` for product names, `###` for each dimension
- Markdown tables for Business Model, Key Risks, and Comparison Matrix
- `>` blockquote for Value Proposition one-liner
- Indented hierarchy or code blocks for Technical Architecture
- **Bold** for key metrics on first mention
- 🔴🟡🟢 for risk severity and feasibility
- `---` horizontal rules between products
- `[N]` inline citations if research was conducted, resolved in a sources section

---

## Quality Checklist

Before delivering, verify:
- [ ] Every dimension is populated (no empty sections)
- [ ] Problem describes real, specific pain (not hypothetical)
- [ ] Evidence includes 3+ data points with numbers or sources
- [ ] Persona is specific enough to find on LinkedIn
- [ ] Value prop is a step-change, not marginal improvement
- [ ] MVP has 3–5 features max
- [ ] Business model shows plausible path to break-even
- [ ] GTM has specific, executable tactics
- [ ] At least one 🔴 Critical risk identified
- [ ] 90-day plan uses nouns (deliverables), not verbs (activities)
- [ ] If multiple products: comparison matrix + build sequence included

---

## Known Limitations

1. **Revenue estimates are directional**: Unit economics at the idea stage establish plausibility, not accuracy. Validate key assumptions with real customer conversations before committing.

2. **Technical architecture is conceptual**: Enough detail to estimate build effort, not a full engineering design document.

3. **Competitive landscape may be incomplete**: Web search captures known competitors; stealth startups and internal tools may be missed.

4. **Persona is illustrative**: Represents a segment, not a real person. Validate through customer discovery interviews.

5. **No financial advice**: Projections are analytical exercises for feasibility testing, not investment-grade forecasts.

6. **90-day plan assumes a small team**: Calibrated for 2–5 people. Solo founders extend; larger teams compress.

7. **Context dependency**: The quality of the output directly depends on the specificity of the user's input. Vague ideas produce less actionable plans.

---

## Example Prompts This Skill Handles

- "Help me plan a product around DeFi risk scoring"
- "I want to build a robo-advisor for crypto yield farming — define the product"
- "Evaluate these 3 business ideas and tell me which to build first"
- "I have a vague idea about AI agents for compliance — help me structure it"
- "Turn the opportunity map from my market research into buildable product specs"
- "Create a business plan for a B2B API that scores DeFi protocol safety"
- "I want to start a company in the prediction market space — what should I build?"
- "my cofounder and I have an idea for a yield optimization tool, help us plan it out"
