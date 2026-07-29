# Phase 5 — UX Strategy

> **Instruction file for Claude Code.**
> Execute this phase after Phase 4 is complete. Output goes to `[project]-ux/research/05-ux-strategy.md`.

---

## Purpose

Align the team on a design direction before wireframes begin. The UX brief produced here is the single reference document for all design decisions that follow. Every wireframe annotation and mockup decision cites one of the principles defined here.

---

## Inputs

- `[project]-ux/00-master-spec.md` — all REQ-IDs and priorities
- `[project]-ux/research/03-synthesis.md` — personas, insights, core themes
- `[project]-ux/research/04-ia.md` — screen inventory, navigation model, user paths

---

## Execution Steps

### Step 1 — Write design principles

Write 3–5 design principles. Each must be:

- **Specific and opinionated** — "Keep it simple" is not a principle. "Surface problems, not progress" is.
- **Derived from research insights** — cite the INSIGHT-ID it comes from
- **Actionable** — must generate a concrete design decision when applied
- **Testable** — you must be able to evaluate whether a design follows it

Format for each principle:

```text
[Principle name]: [One-sentence statement.]
→ In practice: [What this means concretely for design decisions]
→ Not: [What to avoid — the tempting wrong path]
→ Derived from: INSIGHT-0X
```

### Step 2 — Define success metrics

Define measurable UX KPIs in three categories:

- **Behavioural** — task completion rates, time-on-task, clicks-to-complete
- **Attitudinal** — ease-of-use scores, NPS, satisfaction ratings
- **Business** — retention, activation, conversion

For each metric, state a specific target value. If a target cannot be set without baseline data, mark it `[BASELINE NEEDED]`.

### Step 3 — Confirm feature priorities for V1

Using the master spec MoSCoW tags and the insights from research, confirm what ships in V1. If research has changed the priority of any requirement, update it here and note the reason.

Group requirements into:

- Must have (launch blockers)
- Should have (important but not blocking)
- Could have (V1.1 candidates)
- Won't have (explicitly out of scope)

### Step 4 — Write the UX brief

The UX brief is a single condensed document that captures everything needed to design the product. It should be short enough to read in 2 minutes and specific enough to make design decisions from.

It must include: problem statement, primary user, JTBD, design principles (3–5), V1 scope, success criteria, and constraints.

### Step 5 — Write the output file

Use the template below. Every field must be filled with real content — no placeholders.

---

## Output Template

````markdown
# Phase 5 — UX Strategy
Product: [product name]
Date: [date]

---

## Design Principles

### 1. [Principle name]
[One-sentence statement.]

- **In practice:** [Concrete design implication]
- **Not:** [What to avoid]
- **Derived from:** INSIGHT-0X

### 2. [Principle name]
[One-sentence statement.]

- **In practice:** [Concrete design implication]
- **Not:** [What to avoid]
- **Derived from:** INSIGHT-0X

### 3. [Principle name]
[One-sentence statement.]

- **In practice:** [Concrete design implication]
- **Not:** [What to avoid]
- **Derived from:** INSIGHT-0X

---

## Success Metrics (UX KPIs)

### Behavioural metrics
| Metric | Target | Measurement method |
| ------ | ------ | ------------------ |
| [metric, e.g. Time to first meaningful action] | [target, e.g. < 3 min] | [how to measure] |

### Attitudinal metrics
| Metric | Target | Measurement method |
| ------ | ------ | ------------------ |
| Ease-of-use score (post-task survey) | ≥ [value] / 5 | [method] |

### Business metrics
| Metric | Target | Measurement method |
| ------ | ------ | ------------------ |
| 30-day retention | > [value]% | [method] |

---

## Feature Priority — V1 Confirmed

### Must have (launch blockers)
| REQ-ID | Requirement | Research note |
| ------ | ----------- | ------------- |
| REQ-FUNC-001 | [requirement] | [why research confirms this is critical] |

### Should have (important but not blocking)
| REQ-ID | Requirement | Research note |
| ------ | ----------- | ------------- |
| REQ-UX-001 | [requirement] | |

### Could have (V1.1)
| REQ-ID | Requirement | Reason deferred |
| ------ | ----------- | --------------- |
| REQ-FUNC-009 | [requirement] | [reason] |

### Won't have
| REQ-ID | Requirement | Reason excluded |
| ------ | ----------- | --------------- |
| REQ-FUNC-012 | [requirement] | [reason] |

---

## UX Brief

### Problem statement
[2–3 sentences. What problem does this product solve, for whom, and why existing solutions fail them?]

### Primary user
[Persona name] — [one-line description: role, context, key need]

### Primary job to be done
When I [situation], I want to [motivation], so I can [outcome].

### Design principles
1. [Principle 1 name]
2. [Principle 2 name]
3. [Principle 3 name]

### V1 scope
[N] screens. Core flow: [start] → [key step] → [key step] → [end].

### Success criteria
- [Criterion 1 with target value]
- [Criterion 2 with target value]
- [Criterion 3 with target value]

### Constraints
- [Constraint 1 — platform, device, accessibility standard, etc.]
- [Constraint 2]
- [Constraint 3]
````
