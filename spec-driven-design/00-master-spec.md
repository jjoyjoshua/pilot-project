# Phase 0 — Spec Consolidation

> **Instruction file for Claude Code.**
> When the user uploads source documents, execute this phase to produce `[project]-ux/00-master-spec.md`.

---

## Purpose

Unify all input documents into a single, conflict-free spec before any research or design work begins. Every requirement gets a unique REQ-ID. Every design decision made later traces back to one of these IDs.

---

## Inputs

- All documents uploaded by the user (PRDs, spreadsheets, feature lists, emails, Notion exports, etc.)
- Nothing else — do not invent requirements

---

## Execution Steps

### Step 1 — Inventory source documents

List every uploaded document. For each, record:

- Document name and type
- Owner (if stated)
- Date last updated (if stated)
- Format (PDF, Notion, Excel, etc.)

Assign a source ID: `SRC-01`, `SRC-02`, etc.

### Step 2 — Extract all requirements

Read every source document. Extract every functional requirement, constraint, and assumption as a single atomic statement — one requirement = one thing the product must/should/could do.

Rules for extraction:

- Split compound statements into separate requirements ("Users can create and delete projects" → two requirements)
- Rephrase ambiguous statements into testable ones ("should be fast" → "must load in under 2 seconds")
- Capture explicit constraints (technical, legal, timeline) as their own requirements
- Capture assumptions explicitly — label them `ASSUMPTION-XXX`

### Step 3 — Assign REQ-IDs

Format: `REQ-[CATEGORY]-[NUMBER]`

| Category | Meaning |
| -------- | ------- |
| `FUNC` | Functional requirement — what the product does |
| `DATA` | Data / content requirement — what data is stored or displayed |
| `AUTH` | Authentication / permissions / roles |
| `PERF` | Performance, load time, technical constraint |
| `UX` | Usability, accessibility, empty states, error handling |
| `BIZ` | Business rule, pricing, compliance |
| `INT` | Integration, API, third-party dependency |

Number sequentially within each category starting at `001`.

Examples:

```text
REQ-FUNC-001   User must be able to create a new project from the dashboard
REQ-FUNC-002   User must be able to invite team members via email
REQ-AUTH-001   Only admin users can delete a project
REQ-DATA-001   Each project must store: name, description, created_at, owner_id
REQ-UX-001     Empty states must include a call-to-action
REQ-PERF-001   Dashboard must load within 2 seconds on a standard connection
REQ-INT-001    Product must support sign-in via Google OAuth
```

### Step 4 — Apply MoSCoW priorities

Tag each requirement:

| Tag | Meaning |
| --- | ------- |
| `M` | Must have — product cannot launch without this |
| `S` | Should have — important but not launch-blocking |
| `C` | Could have — nice to have if time and scope allow |
| `W` | Won't have — explicitly out of scope for this version |

If priority is not stated in the source documents, apply your best judgement and flag it: `[ASSUMED — confirm with product owner]`.

### Step 5 — Detect and flag conflicts

Look for requirements that contradict each other. Flag with `⚠ CONFLICT`:

```text
REQ-FUNC-007   Dashboard shows all projects by default                [M]
REQ-FUNC-008   Dashboard shows only the user's own projects           [M]
⚠ CONFLICT: REQ-FUNC-007 vs REQ-FUNC-008 — scope of "all" is ambiguous. Clarify with product owner.
```

Common conflict types to check:

- Scope conflicts (all vs. mine vs. team)
- Permission conflicts (who can do what)
- State conflicts (default behaviour contradictions)
- Technical conflicts (two requirements that cannot both be satisfied)

### Step 6 — Write the output file

Write the completed master spec to `[project]-ux/00-master-spec.md` using the template below.

---

## Output Template

```markdown
# Master Spec — [Product Name]
Last updated: [date]
Version: 1.0
Status: Draft

---

## Sources

| ID | Document | Type | Owner | Date |
| -- | -------- | ---- | ----- | ---- |
| SRC-01 | [document name] | [PRD / spreadsheet / etc.] | [name] | [date] |

---

## Requirements

### Functional
| REQ-ID | Requirement | Priority | Source | Status |
| ------ | ----------- | -------- | ------ | ------ |
| REQ-FUNC-001 | [requirement] | M | SRC-01 | Open |

### Data
| REQ-ID | Requirement | Priority | Source | Status |
| ------ | ----------- | -------- | ------ | ------ |
| REQ-DATA-001 | [requirement] | M | SRC-01 | Open |

### Authentication & Permissions
| REQ-ID | Requirement | Priority | Source | Status |
| ------ | ----------- | -------- | ------ | ------ |
| REQ-AUTH-001 | [requirement] | M | SRC-01 | Open |

### Performance & Technical
| REQ-ID | Requirement | Priority | Source | Status |
| ------ | ----------- | -------- | ------ | ------ |
| REQ-PERF-001 | [requirement] | S | SRC-01 | Open |

### UX Requirements
| REQ-ID | Requirement | Priority | Source | Status |
| ------ | ----------- | -------- | ------ | ------ |
| REQ-UX-001 | [requirement] | S | SRC-01 | Open |

### Business Rules
| REQ-ID | Requirement | Priority | Source | Status |
| ------ | ----------- | -------- | ------ | ------ |
| REQ-BIZ-001 | [requirement] | M | SRC-01 | Open |

### Integrations
| REQ-ID | Requirement | Priority | Source | Status |
| ------ | ----------- | -------- | ------ | ------ |
| REQ-INT-001 | [requirement] | C | SRC-01 | Open |

---

## Assumptions

| ID | Assumption | Validation needed from |
| -- | ---------- | ---------------------- |
| ASSUMPTION-001 | [assumption] | [owner] |

---

## Open Conflicts

| Conflict ID | Description | REQ-IDs involved | Resolution needed from |
| ----------- | ----------- | ---------------- | ---------------------- |
| CONFLICT-001 | [description] | REQ-FUNC-007, REQ-FUNC-008 | Product owner |

---

## Open Questions

- [ ] [question] → needs answer from: [owner]

---

## Summary Statistics

- Total requirements: [N]
- Must have: [N]
- Should have: [N]
- Could have: [N]
- Won't have: [N]
- Open conflicts: [N]
- Open questions: [N]
```
