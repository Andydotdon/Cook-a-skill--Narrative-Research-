# Market Research → Product Definition Pipeline

## What Is This?

This is a two-skill system that takes you from **"is this market real?"** to **"here's exactly what I should build"** — with structured, evidence-backed documents at each stage.

Think of it as your personal strategy analyst. You give it a topic. It researches the market, validates demand, maps competitors, identifies opportunities, and then turns the best opportunity into a concrete product plan with features, pricing, architecture, go-to-market, and a 90-day build plan.

The two skills are:

```
┌─────────────────────┐          ┌─────────────────────┐
│  narrative-research  │  ─────▶  │  business-idea-plan  │
│                      │          │                      │
│  "Is this real?"     │          │  "What do I build?"  │
│                      │          │                      │
│  11-section market   │          │  12-dimension product │
│  validation report   │          │  definition           │
└─────────────────────┘          └─────────────────────┘
```

You can use them together as a pipeline or independently. Neither requires the other.

---

## How the Pipeline Works (With a Real Example)

Here's how we used these skills to go from "I'm curious about OpenClaw" to "here's a buildable product with a 90-day plan":

### Step 1 → Narrative Research

**You say**: "Do a narrative research on OpenClaw"

**What happens**: The skill runs 5–10 web searches, gathers evidence, and produces an 11-section Markdown report covering thesis, market size ($7.6B AI agents market), demand proof (160K GitHub stars, 300K+ users), competitor mapping (34+ agent platforms), risks (512 vulnerabilities found), and 5 product opportunities.

**Output**: `OpenClaw_Narrative_Research_Feb2026.md`

### Step 2 → Deeper Ideation (Optional)

**You say**: "None of the ideas attract my interest. I need new ideas"

**What happens**: The deeper ideation mode activates within the narrative-research skill. It uses 6 ideation techniques (invert the thesis, follow friction, cross-pollinate, stack weaknesses, serve builders, shrink scope) to generate 8–12 fresh concepts organized by archetype (Contrarian Bet, Picks & Shovels, Vertical Wedge, Bridge Product, Intelligence Product, Trust Layer).

**Output**: `OpenClaw_Deeper_Ideation_Feb2026.md` — 10 new concepts with a comparison matrix

### Step 3 → Business Idea Plan

**You say**: "I'm most interested in DeadManSwitch. Help me do the business idea plan"

**What happens**: The business-idea-plan skill takes the chosen concept and produces a 12-dimension product definition — grounded in the research evidence from Step 1. It runs additional targeted searches to fill gaps (competitor tools, incident details, pricing benchmarks).

**Output**: `DeadManSwitch_Business_Idea_Plan_Feb2026.md` — a complete product plan ready to execute

### The Full Journey

```
"I'm curious about OpenClaw"
        │
        ▼
   narrative-research
   (11 sections, 10 web searches)
        │
        ▼
   5 opportunities identified
        │
        ▼
   "None excite me"
        │
        ▼
   Deeper Ideation Mode
   (10 fresh concepts, 6 techniques)
        │
        ▼
   "I like DeadManSwitch"
        │
        ▼
   business-idea-plan
   (12 dimensions, targeted research)
        │
        ▼
   Buildable product plan with
   90-day timeline and revenue model
```

---

## Skill 1: narrative-research

### What It Produces

A thesis-driven market validation report. It starts with a falsifiable hypothesis ("this market is real because X, Y, Z") and systematically gathers evidence to support, challenge, or refine it.

### The 11 Sections

| # | Section | What You Learn |
|---|---------|---------------|
| 1 | Narrative Thesis | A clear, falsifiable statement about the market |
| 2 | Why Now? Catalysts | What changed to make this possible today |
| 3 | Market Sizing | How big is this, with real numbers and sources |
| 4 | Demand Validation | Proof that real people want this (not just hype) |
| 5 | Supply-Side Map | Who's building, and how they compare |
| 6 | Key Player Deep Dive | Operational analysis of top players — strengths, weaknesses, metrics |
| 7 | Validation Scorecard | Honest red/yellow/green assessment across 7–8 dimensions |
| 8 | Risks & Counter-Narratives | The best arguments for why this trend *fails* |
| 9 | Analogies | Historical patterns — what does this remind us of? |
| 10 | Opportunity Map | 4–5 specific product ideas with evidence and first steps |
| 11 | Sources & Methodology | Every source cited, plus honest limitations |

### Deeper Ideation Mode

If Section 10's opportunities don't excite you, say so. The skill shifts into an expanded ideation mode that generates 8–12 concepts using six creative techniques, organized into six archetypes:

- 🛠️ **Picks & Shovels** — sell tools to the gold miners
- 🛡️ **Trust Layer** — solve the security/compliance gap
- 🎯 **Vertical Wedge** — own one niche deeply
- 🌉 **Bridge Product** — connect two ecosystems
- 📊 **Intelligence Product** — sell insight, not software
- 🔮 **Contrarian Bet** — bet against the consensus

### When to Use It

Use narrative-research when you're evaluating a market, trend, or space — before you've committed to a specific product idea. It's the "should I even be here?" question.

---

## Skill 2: business-idea-plan

### What It Produces

A structured product definition that answers every question you need answered before writing code. Each of the 12 dimensions targets a specific way products fail.

### The 12 Dimensions

| # | Dimension | Prevents This Failure |
|---|-----------|----------------------|
| 1 | Product Name & Tagline | "I can't explain what I'm building" |
| 2 | Problem Statement | "I'm solving an imagined problem" |
| 3 | Evidence From Research | "I have no proof anyone wants this" |
| 4 | Target User Persona | "I'm building for everyone (= nobody)" |
| 5 | Value Proposition | "It's a marginal improvement nobody will switch for" |
| 6 | Core Feature Set (MVP) | "I'm building too much before validating" |
| 7 | Technical Architecture | "This requires technology that doesn't exist" |
| 8 | Business Model & Unit Economics | "I have no idea how to make money" |
| 9 | Go-To-Market Strategy | "Great product, no users" |
| 10 | Competitive Moat | "Competitors will copy and outspend me" |
| 11 | Key Risks & Mitigations | "I didn't see the thing that killed me" |
| 12 | 90-Day Build Plan | "I have a document but no action plan" |

### Three Entry Points

1. **You have a specific idea** → goes straight to the 12-dimension plan
2. **You have a domain but no idea** → generates 3–5 quick concepts, you pick, then full plan
3. **You're coming from narrative-research** → pulls evidence from the research to ground the plan

### When to Use It

Use business-idea-plan when you've identified something you want to build and need to turn the concept into a concrete, actionable plan. It's the "what exactly am I building?" question.

---

## File Structure

```
outputs/
├── README.md                          ← You are here
│
├── narrative-research-skill/          ← The market validation skill
│   ├── SKILL.md                       ← Full instructions Claude follows
│   ├── SPEC_SUMMARY.md                ← Human-readable overview
│   └── evals/
│       └── evals.json                 ← Test cases for validation
│
├── business-idea-plan-skill/          ← The product definition skill
│   ├── SKILL.md                       ← Full instructions Claude follows
│   ├── SPEC_SUMMARY.md                ← Human-readable overview
│   └── evals/
│       └── evals.json                 ← Test cases for validation
│
├── OpenClaw_Narrative_Research_Feb2026.md    ← Example output: market research
├── OpenClaw_Deeper_Ideation_Feb2026.md      ← Example output: expanded ideas
└── DeadManSwitch_Business_Idea_Plan_Feb2026.md  ← Example output: product plan
```

### What Each File Type Does

| File | Who reads it | Purpose |
|------|-------------|---------|
| **SKILL.md** | Claude (the AI) | Detailed instructions for generating the output. This is the "recipe" — it tells Claude exactly what sections to include, what quality bars to hit, and how to format everything. You don't need to read this unless you want to modify how the skill works. |
| **SPEC_SUMMARY.md** | You (the human) | A plain-language overview of what the skill does, how it works, and what to expect. Read this to understand the skill without wading through implementation details. |
| **evals.json** | Anyone testing the skill | Example prompts with expected outputs. Use these to verify the skill produces good results, or as inspiration for your own prompts. |
| **Output .md files** | You | The actual deliverables — research reports and product plans. These are what you share with cofounders, investors, or yourself. |

---

## How to Use These Skills

### If You're Using Claude with Custom Skills

Copy the `narrative-research-skill/` and `business-idea-plan-skill/` folders into your skills directory. Claude will automatically detect and use them when your prompts match the trigger conditions.

### If You're Just Using Claude Normally

You don't need to install anything. Just reference the frameworks in your prompt:

- "Research [topic] using the 11-section narrative research framework"
- "Create a 12-dimension product plan for [idea]"
- Or simply share the SKILL.md content as context in your conversation

### Prompts That Trigger Each Skill

**narrative-research** activates on:
- "Research the [X] market for me"
- "Is [trend] real or hype?"
- "Do a deep dive on [space]"
- "Validate whether [opportunity] is worth pursuing"

**business-idea-plan** activates on:
- "Help me plan a product around [X]"
- "I want to build [X] — define the product"
- "Turn these opportunities into product specs"
- "Evaluate this business idea"

**Deeper ideation** activates on:
- "These ideas don't excite me"
- "Give me more creative ideas"
- "None of these fit my skills"

---

## Design Principles

A few things that were deliberately chosen and why:

**Markdown output, not Word/PDF.** Markdown renders everywhere — Claude artifacts, GitHub, Notion, VS Code, any text editor. Zero dependencies. No broken formatting.

**Thesis-first, not data-first.** The research skill starts with a falsifiable hypothesis, then gathers evidence. This prevents the "I have 50 data points but no conclusion" problem. If the thesis is wrong, the evidence tells you.

**Every dimension prevents a failure mode.** The 12-dimension framework isn't arbitrary. Each dimension exists because skipping it causes a specific, common product failure. They're ordered so that each builds on the previous one.

**At least one red rating required.** The validation scorecard must include at least one 🟡 or 🔴. All-green means you haven't looked hard enough. The risks section must include at least one 🔴 Critical risk. This keeps the analysis honest.

**The two skills are independent but composable.** You can run narrative-research without ever using business-idea-plan, and vice versa. But when used in sequence, the research evidence flows directly into the product plan — every claim in the product definition traces back to data from the research.

**Deeper ideation stays inside narrative-research.** When you reject the initial opportunities, you don't switch skills. The same research context powers the expanded ideation, so every new concept is grounded in the evidence already gathered.
