# Phase 2 — User Research

> **Instruction file for Claude Code.**
> Execute this phase after Phase 1 is complete. Output goes to `[project]-ux/research/02-user-research.md`.

---

## Purpose

Validate or challenge the assumptions baked into the requirements. Understand who the real users are, what they actually need, and where they currently struggle.

---

## Inputs

- `[project]-ux/00-master-spec.md` — requirements and assumptions
- `[project]-ux/research/01-discovery.md` — unvalidated assumptions, competitor context
- Any user interview transcripts, survey data, or analytics reports shared by the user

---

## Execution Steps

### Step 1 — Choose research methods

Select the appropriate methods based on what the user has provided. Apply all methods for which input data exists.

| Method | When to use | Input needed |
| ------ | ----------- | ------------ |
| Analytics review | Existing product with usage data | Analytics export |
| Survey synthesis | Quantitative signal across many users | Survey results |
| Interview synthesis | Deep qualitative insight | Interview transcripts or notes |
| Contextual inquiry notes | Observed real behaviour | Field notes |

If no primary research data is provided, synthesise from the requirements and assumptions. Note clearly: `[SYNTHESISED FROM REQUIREMENTS — validate with real users before wireframing]`.

### Step 2 — Synthesise per-participant data

For each participant (or data source), produce a structured summary covering: role, tools used, key quotes, behaviours observed, pain points, and goals.

### Step 3 — Identify cross-participant patterns

Across all participants, look for:

- Pain points mentioned by 3 or more participants
- Mental model patterns (how users conceptualise the product domain)
- Vocabulary patterns (the exact words users use — these inform labelling in Phase 4)
- Behaviour patterns (workarounds, tool-switching, frequency of tasks)

### Step 4 — Build the vocabulary table

Capture the words users actually use vs. what the product currently uses or what internal teams call things. This directly informs labelling decisions in Phase 4 (IA).

### Step 5 — Write the output file

Produce a participant summary for every data source, then a cross-participant synthesis. Use the template below.

---

## Interview Guide Template

Use this when conducting or reviewing interviews:

```text
INTERVIEW GUIDE — [Product Name]
Duration: 45–60 minutes

WARM-UP (5 min)
- Tell me about your role and what you do day-to-day.
- What tools do you use most for [relevant task]?

CURRENT BEHAVIOUR (15 min)
- Walk me through the last time you [key task from requirements].
- What did you use? How did it go?
- What was frustrating about that experience?
- What worked well?

MENTAL MODELS (10 min)
- How do you think about [core concept in the product]?
- How would you describe [feature area] to a colleague?

NEEDS & PAIN POINTS (15 min)
- What is the hardest part of [job to be done]?
- If you could change one thing, what would it be?
- What does "good" look like for you here?

WRAP-UP (5 min)
- Is there anything I haven't asked that you think is important?
- Who else on your team should I talk to?
```

---

## Output Template

````markdown
# Phase 2 — User Research
Product: [product name]
Date: [date]
Research methods used: [list methods applied]

---

## Participant Summaries

### Participant P01
- **Role:** [job title, company type]
- **Team size:** [number]
- **Experience with this type of product:** [novice / intermediate / expert]
- **Primary device:** [desktop / mobile / both]
- **Current tools:** [tools they use today for this job]

#### Key quotes
> "[direct quote]"
> "[direct quote]"

#### Behaviours observed
- [behaviour 1]
- [behaviour 2]

#### Pain points
- [pain point 1]
- [pain point 2]

#### Goals
- [goal 1]
- [goal 2]

#### Assumptions validated / invalidated
| Assumption ID | Status | Evidence |
| ------------- | ------ | -------- |
| ASSUMPTION-001 | ✅ Validated | [evidence] |
| ASSUMPTION-002 | ❌ Invalidated | [evidence] |

---

### Participant P02
[same structure]

---

## Cross-Participant Patterns

### Recurring pain points

| Pain point | Participants | Frequency |
| ---------- | ------------ | --------- |
| [pain point] | P01, P03, P05 | 3 of [N] |

### Mental model notes

- [mental model observation 1]
- [mental model observation 2]

### Vocabulary used

| Users say | Internal / assumed term | Decision |
| --------- | ----------------------- | -------- |
| "[word]" | "[word]" | Use "[user term]" |

### Behaviour patterns

- [pattern 1 — e.g. "All participants checked status first thing in the morning"]
- [pattern 2]

---

## Assumption Audit

| Assumption ID | Assumption | Status | Evidence | Impact on design |
| ------------- | ---------- | ------ | -------- | ---------------- |
| ASSUMPTION-001 | [assumption] | ✅ Validated | [evidence] | [implication] |
| ASSUMPTION-002 | [assumption] | ❌ Invalidated | [evidence] | [implication] |
| ASSUMPTION-003 | [assumption] | ⚠ Unclear | [evidence] | [implication] |

---

## Open Questions for Synthesis

- [ ] [question raised by research that needs answering in Phase 3]
````
