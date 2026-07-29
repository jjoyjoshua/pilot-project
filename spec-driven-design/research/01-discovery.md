# Phase 1 — Discovery

> **Instruction file for Claude Code.**
> Execute this phase after Phase 0 is complete. Output goes to `[project]-ux/research/01-discovery.md`.

---

## Purpose

Understand the problem space, constraints, and competitive landscape from the requirements and market context — without stakeholder interviews. Define the initial screen inventory.

---

## Inputs

- `[project]-ux/00-master-spec.md` — consolidated requirements and REQ-IDs

---

## Execution Steps

### Step 1 — Requirements audit

Read the master spec and answer each of the following. Write direct, specific answers — not placeholders.

- What problem is this product fundamentally solving?
- Who is it for at a rough level (role, context, scale)?
- What are the hard constraints (technical, legal, timeline, platform)?
- What assumptions are baked into the requirements that have not been validated?

For each unvalidated assumption, document it explicitly:

```text
ASSUMPTION-001: [assumption statement]
ASSUMPTION-002: [assumption statement]
```

Assumptions come from reading between the lines of the requirements — things that are implied but never stated. Examples: "users are on desktop", "teams are small", "users are technical".

### Step 2 — Competitor audit

Identify 3–5 direct or indirect competitors. For each, document the UX patterns — not features. Focus on what design decisions are worth borrowing vs. avoiding for this product.

For each competitor:

```text
Competitor: [name]
Primary use case: [what it does]
Navigation model: [sidebar / top bar / hub-spoke / etc.]
Onboarding: [how they handle first-time users]
Empty states: [what they show when no data exists]
Strength: [what they do well UX-wise]
Weakness: [where they fail UX-wise]
Borrow: [specific patterns worth adopting]
Avoid: [specific patterns to stay away from]
```

### Step 3 — Heuristic evaluation (only if redesign)

If this is a redesign of an existing product, evaluate the current product against Nielsen's 10 heuristics. Score each 0–4:

- 0 = Catastrophic usability failure
- 1 = Major issue, must fix
- 2 = Minor issue, should fix
- 3 = Small issue, could fix
- 4 = No issue

Heuristics: Visibility of system status · Match between system and real world · User control and freedom · Consistency and standards · Error prevention · Recognition rather than recall · Flexibility and efficiency of use · Aesthetic and minimalist design · Help users recognise and recover from errors · Help and documentation

### Step 4 — Define V1 scope

Using the master spec priorities, define what is in and out of scope:

- **V1 scope:** All `M` requirements + any `S` requirements confirmed by the user
- **Out of scope:** All `W` requirements + deprioritised `C` requirements

### Step 5 — Draft screen inventory

From the V1 scope, derive the minimum set of screens required. Assign a sequential SCR-ID to each.

Rules:

- Only create screens that at least one `M` or confirmed `S` requirement demands
- Include error and empty states as separate screen entries
- Do not include screens for `W` requirements
- This is a draft — it will be finalised in Phase 4 (IA)

---

## Output Template

````markdown
# Phase 1 — Discovery
Product: [product name]
Date: [date]

---

## Requirements Audit

### Problem statement
[One paragraph. What problem does this product solve, for whom, and in what context?]

### Target users
[Role, company size, technical level, primary device]

### Hard constraints
| Constraint | Type | Source |
| ---------- | ---- | ------ |
| [constraint] | Technical / Legal / Timeline / Platform | REQ-ID or SRC-ID |

### Unvalidated assumptions
| ID | Assumption | Risk if wrong |
| -- | ---------- | ------------- |
| ASSUMPTION-001 | [assumption] | [what breaks if this is wrong] |

---

## Competitor Audit

### Competitor 1 — [name]
- **Primary use case:** [description]
- **Navigation model:** [pattern]
- **Onboarding:** [how they handle it]
- **Empty states:** [what they show]
- **Strength:** [UX strength]
- **Weakness:** [UX weakness]
- **Borrow:** [specific patterns]
- **Avoid:** [specific patterns]

### Competitor 2 — [name]
[same structure]

### Competitor 3 — [name]
[same structure]

---

## Heuristic Evaluation (if redesign)

| Heuristic | Score (0–4) | Issue | Severity |
| --------- | ----------- | ----- | -------- |
| Visibility of system status | [0–4] | [issue description] | [critical/major/minor] |
| Match with real world | [0–4] | | |
| User control and freedom | [0–4] | | |
| Consistency and standards | [0–4] | | |
| Error prevention | [0–4] | | |
| Recognition over recall | [0–4] | | |
| Flexibility and efficiency | [0–4] | | |
| Aesthetic and minimalist design | [0–4] | | |
| Error recovery | [0–4] | | |
| Help and documentation | [0–4] | | |

---

## V1 Scope

### In scope
| REQ-ID | Requirement | Priority |
| ------ | ----------- | -------- |
| REQ-FUNC-001 | [requirement] | M |

### Out of scope
| REQ-ID | Requirement | Reason out |
| ------ | ----------- | ---------- |
| REQ-FUNC-009 | [requirement] | W — future version |

---

## V1 Screen Inventory (draft)

| SCR-ID | Screen name | REQ-IDs it fulfils | Notes |
| ------ | ----------- | ------------------ | ----- |
| SCR-01 | [name] | REQ-FUNC-001 | |
| SCR-02 | [name] | REQ-FUNC-005 | |

**Total screens in V1 scope:** [N]

> This is a draft. The screen inventory is finalised in Phase 4 (IA) after card sorting and sitemap work.
````
