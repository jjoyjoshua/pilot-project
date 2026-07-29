# Spec-Driven Design — Pipeline Execution Guide

> This is the master instruction file for Claude Code.
> Read this file first whenever the user uploads requirement documents.

---

## What This Folder Is

`spec-driven-design/` is the **pipeline engine** — it contains the instructions, rules, and output templates that drive the entire design process. It does not contain project-specific content.

When the pipeline runs, a **separate project output folder** is created. All research, screen specs, wireframe specs, and design system files for the actual project go there — not here.

---

## Pipeline Trigger

**Start the pipeline when** the user uploads one or more source documents (PRD, feature list, spreadsheet, Notion export, email thread, etc.).

Do not start without at least one source document. If the user says "start the pipeline" without uploading a file, ask: "Please share your requirements document to begin."

---

## Step 0 — Name the Project and Create the Output Folder

Ask the user: "What is the name of this project?" Use the answer to name the output folder:

```text
[project-name]-ux/
```

Create the following structure immediately. Do **not** create `screens/` yet — it is generated after Phase 4.

```text
[project-name]-ux/
├── 00-master-spec.md
├── research/
│   ├── 01-discovery.md
│   ├── 02-user-research.md
│   ├── 03-synthesis.md
│   ├── 04-ia.md
│   ├── 05-ux-strategy.md
│   └── 06-concept-validation.md
├── wireframe-rules/
│   ├── grid-system.md
│   ├── spacing-variables.md
│   ├── color-variables.md
│   └── component-set.md
├── design-system/
│   ├── color-system.md
│   ├── typography-system.md
│   ├── spacing-tokens.md
│   ├── component-library.md
│   └── sign-off.md
└── figma/
    ├── figma-file-structure.md
    └── mcp-generation-rules.md
```

Copy the content from `spec-driven-design/wireframe-rules/` and `spec-driven-design/figma/` verbatim into the project folder — these are fixed standards. The research and design-system files are filled in per-project.

---

## Execution Sequence

Run each step in order. Do not skip steps. Do not proceed past a sign-off gate without user confirmation.

| Step | Action | Instruction file | Output file |
| ---- | ------ | ---------------- | ----------- |
| 0 | Spec consolidation | `spec-driven-design/00-master-spec.md` | `[project]-ux/00-master-spec.md` |
| 1 | Discovery | `spec-driven-design/research/01-discovery.md` | `[project]-ux/research/01-discovery.md` |
| 2 | User research | `spec-driven-design/research/02-user-research.md` | `[project]-ux/research/02-user-research.md` |
| 3 | Synthesis | `spec-driven-design/research/03-synthesis.md` | `[project]-ux/research/03-synthesis.md` |
| 4 | Information architecture | `spec-driven-design/research/04-ia.md` | `[project]-ux/research/04-ia.md` |
| 4b | **Create screens/ folder** | See below | `[project]-ux/screens/SCR-XX-name.md` |
| 5 | UX strategy | `spec-driven-design/research/05-ux-strategy.md` | `[project]-ux/research/05-ux-strategy.md` |
| 6 | Concept validation | `spec-driven-design/research/06-concept-validation.md` | `[project]-ux/research/06-concept-validation.md` |
| 7 | Wireframes | `spec-driven-design/figma/mcp-generation-rules.md` | Figma — one page per screen |
| ◆ | **GATE: Wireframe sign-off** | `spec-driven-design/design-system/sign-off.md` | User confirms before Step 8 |
| 8 | Design system — foundations | `spec-driven-design/design-system/` | `[project]-ux/design-system/` filled in |
| 9 | Design system — components | `spec-driven-design/design-system/component-library.md` | Figma component library |
| ◆ | **GATE: Design system sign-off** | `spec-driven-design/design-system/sign-off.md` | User confirms before Step 10 |
| 10 | Hi-fi mockups | `spec-driven-design/figma/mcp-generation-rules.md` | Figma — one page per screen |

---

## Step 4b — Creating the screens/ Folder

This step runs **immediately after Phase 4 (IA) is complete** and the screen inventory is confirmed.

1. Read the finalised screen inventory from `[project]-ux/research/04-ia.md`
2. Create `[project]-ux/screens/`
3. For each screen in the inventory, create one spec file: `SCR-[ID]-[screen-name].md`
4. Use the per-screen spec format defined in `spec-driven-design/research/04-ia.md § Per-Screen Spec Template`
5. Pre-fill each file with the REQ-IDs, IA position, and persona pulled from the research output files

Do not invent screen names. Every SCR-ID must appear in the Phase 4 sitemap.

---

## Sign-Off Gate Rules

At each gate, **stop** and present the sign-off checklist to the user. Do not proceed until the user explicitly confirms.

**Gate 1 — Wireframe sign-off:**
Present checklist from `spec-driven-design/design-system/sign-off.md § Gate 1`.
On confirmation: lock wireframe work, begin design system build.

**Gate 2 — Design system sign-off:**
Present checklist from `spec-driven-design/design-system/sign-off.md § Gate 2`.
On confirmation: lock design system, begin hi-fi mockup generation.

---

## Rules for All Output Files

- Every output file references the REQ-IDs it relates to
- No placeholder text left in output files — every section is filled with real content derived from the source documents
- If information is genuinely unknown, mark it `[OPEN QUESTION — needs input from: (owner)]` rather than leaving it blank
- Mermaid diagrams must render correctly — test syntax before writing to file
