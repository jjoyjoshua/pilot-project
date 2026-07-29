# Phase 3 — Synthesis

> **Instruction file for Claude Code.**
> Execute this phase after Phase 2 is complete. Output goes to `[project]-ux/research/03-synthesis.md`.

---

## Purpose

Transform raw research into shared, actionable understanding. Move from "here is what we heard" to "here is what it means and what we should design for."

---

## Inputs

- `[project]-ux/00-master-spec.md` — requirements and REQ-IDs
- `[project]-ux/research/01-discovery.md` — assumptions and competitor patterns
- `[project]-ux/research/02-user-research.md` — participant summaries, cross-participant patterns, vocabulary

---

## Execution Steps

### Step 1 — Affinity mapping

Group every observation, quote, and behaviour from Phase 2 into bottom-up themes. Each theme represents a cluster of related pain points or needs.

Rules:

- Name themes from the user's perspective, not the product's (e.g. "Lack of visibility" not "Missing dashboard feature")
- Every theme must contain at least 2 distinct observations
- Maximum 8 themes — if you have more, merge related ones
- Each theme becomes a design opportunity in Step 4 (HMW)

### Step 2 — Build personas

Derive 1–3 personas from real research patterns. Rules:

- Each persona must be grounded in data from Phase 2 — not invented
- Include only patterns seen in 2+ participants
- Each persona must reference the REQ-IDs it drives
- Primary persona = the one who uses the product most frequently or whose job is most critical

### Step 3 — Journey map

Map the **current** experience (not the ideal future state) for the primary persona completing the primary job to be done. Stages should reflect the real sequence of steps the user takes today, including workarounds and pain points.

Columns = stages of the journey. Rows = Action / Thought / Emotion / Pain point / Opportunity.

### Step 4 — How Might We (HMW)

Reframe each theme from Step 1 as a design question. Format: "HMW [verb] [user] [desired outcome]?"

Rules:

- One HMW per theme — do not split themes
- HMW questions should be broad enough to allow multiple solutions, narrow enough to provide direction
- Bad: "HMW make the dashboard better?" (too vague)
- Good: "HMW give the PM a complete picture of team progress in under 10 seconds?" (specific, measurable)

### Step 5 — Core insights

Distil everything into 5–8 insight statements. Each insight must be:

- Specific enough to make a design decision from
- Derived from research — not from requirements alone
- Paired with a direct design implication

Format: `INSIGHT-XX: [observation]. → Design for: [specific design direction].`

### Step 6 — Write the output file

Use the template below. Every section must be fully populated — no placeholders.

---

## Output Template

````markdown
# Phase 3 — Synthesis
Product: [product name]
Date: [date]

---

## Affinity Map Themes

### Theme 1 — [Theme name from user perspective]
**Observations:**
- "[quote or behaviour]" — P01
- "[observation]" — P03, P05

**Design opportunity:** [one sentence on what this theme points toward]

### Theme 2 — [Theme name]
**Observations:**
- [observation] — P02

**Design opportunity:** [one sentence]

[Repeat for all themes — minimum 3, maximum 8]

---

## Personas

### Persona — "[Persona nickname]"

| Field | Detail |
| ----- | ------ |
| Name | [fictional name] |
| Role | [job title] |
| Company size | [range] |
| Experience | [years in role] |
| Primary device | [desktop / mobile / both] |
| Context of use | [when / where / how often] |

#### Goals
- [goal 1]
- [goal 2]
- [goal 3]

#### Pain points
- [pain point 1]
- [pain point 2]
- [pain point 3]

#### Mental model
[How this persona conceptualises the problem space — 2–3 sentences]

#### Representative quote
> "[a quote that captures this persona's mindset — real or synthesised from research]"

#### REQ-IDs this persona drives
[REQ-FUNC-001, REQ-UX-001, ...]

---

## Journey Map — [Persona name] [Job to be done]

| | [Stage 1] | [Stage 2] | [Stage 3] | [Stage 4] |
| -- | --------- | --------- | --------- | --------- |
| **Action** | [what they do] | | | |
| **Thought** | "[what they're thinking]" | | | |
| **Emotion** | [😕 Frustrated / 😤 Annoyed / etc.] | | | |
| **Pain point** | [specific pain] | | | |
| **Opportunity** | [design opportunity] | | | |

---

## How Might We (HMW)

| Theme | HMW statement |
| ----- | ------------- |
| [Theme 1 name] | HMW [verb] [user] [desired outcome]? |
| [Theme 2 name] | HMW … |

---

## Core Insights

| ID | Insight | Design implication |
| -- | ------- | ------------------ |
| INSIGHT-01 | [specific observation from research] | → Design for: [specific design direction] |
| INSIGHT-02 | [observation] | → Design for: [direction] |
| INSIGHT-03 | [observation] | → Design for: [direction] |
| INSIGHT-04 | [observation] | → Design for: [direction] |
| INSIGHT-05 | [observation] | → Design for: [direction] |

---

## Synthesis Summary

**Primary persona:** [name and one-line description]
**Primary job to be done:** When I [situation], I want to [motivation], so I can [outcome].
**Top 3 design priorities derived from research:**
1. [priority]
2. [priority]
3. [priority]
````
