# Design System — Sign-Off Gates

> **Instruction file for Claude Code.**
> At each gate, stop the pipeline, present the checklist to the user, and wait for explicit confirmation before continuing.
> Do not proceed past a gate without user sign-off.

---

## How Claude Code uses this file

**At Gate 1:** After all wireframe frames are generated in Figma, present the Gate 1 checklist below to the user. Pause. Wait for the user to confirm each item. On confirmation, lock wireframe pages (note in the project's `figma/figma-file-structure.md` that wireframe pages are signed off) and begin design system foundation work.

**At Gate 2:** After all design system tokens and components are built in Figma, present the Gate 2 checklist to the user. Pause. Wait for explicit sign-off. On confirmation, begin hi-fi mockup generation.

If the user flags any checklist item as not complete, stop. Do not proceed until the issue is resolved.

---

## Gate 1 — Wireframe Sign-Off

Present this checklist to the user after all wireframes are complete:

```text
WIREFRAME SIGN-OFF CHECKLIST

COVERAGE
[ ] All screens in the confirmed screen inventory have wireframe frames in Figma
[ ] All states for each screen are wireframed (default, empty, loading, error)
[ ] All spec annotation panels are complete (REQ-IDs, persona, principle, open questions)
[ ] All open questions from concept validation are documented on the relevant screen spec

STRUCTURE
[ ] All frames use the grid defined in wireframe-rules/grid-system.md
[ ] All spacing uses variables from wireframe-rules/spacing-variables.md only — no raw pixel values
[ ] All components are from the lo-fi set in wireframe-rules/component-set.md
[ ] Auto layout applied to every frame and component — no manually positioned elements

TRACEABILITY
[ ] Every screen spec references the REQ-IDs it fulfils
[ ] Every wireframe annotation panel matches the screen spec file in screens/

REVIEW
[ ] Reviewed by: [Design lead]
[ ] Reviewed by: [Product lead]
[ ] Reviewed by: [Engineering lead] (feasibility check)

Date signed off: ___________
Signed by: ___________
```

**On sign-off:** Update `figma/figma-file-structure.md` status tracker. Note wireframe pages as locked. Begin design system foundation build.

---

## Gate 2 — Base Variables Confirmed (Pre-Component Gate)

Present this intermediate checklist before building any component:

```text
BASE VARIABLES CHECKLIST

COLOR
[ ] All primitive color tokens defined (full scale for brand, neutral, semantic colors)
[ ] All semantic tokens defined and aliased to primitives
[ ] Dark mode aliases defined (if in scope)
[ ] All text/background combinations checked for WCAG AA contrast (minimum 4.5:1)

TYPOGRAPHY
[ ] All text styles created in Figma (full scale from caption to display-2xl)
[ ] Font files loaded and licensed
[ ] Line height and letter spacing verified at each scale step

SPACING
[ ] Spacing scale defined as Number variables (space-2 through space-80)
[ ] Border radius tokens defined (radius-none through radius-full)
[ ] Elevation styles created (elevation-0 through elevation-4)
[ ] Icon size tokens defined (icon-xs through icon-xl)
[ ] Component size tokens defined (size-xs through size-xl)

Sign-off required from: [Design lead] + [Dev lead]
Date confirmed: ___________
```

**On confirmation:** Begin building Tier 1 components.

---

## Gate 3 — Design System Sign-Off (Pre-Hi-Fi Gate)

Present this checklist to the user after all design system tokens and components are complete:

```text
DESIGN SYSTEM SIGN-OFF CHECKLIST

TOKENS
[ ] All primitive tokens defined (color, spacing, radius, elevation, icon sizes)
[ ] All semantic tokens defined and aliased to primitives
[ ] All component tokens defined and aliased to semantic tokens
[ ] No component uses a raw value — every property references a named token

COMPONENTS
[ ] All Tier 1 atoms built with full variant matrices
[ ] All Tier 2 base components built with full variant matrices
[ ] All Tier 3 composite components built with full variant matrices
[ ] All Tier 4 page patterns built
[ ] Dark mode variants built (if in scope)

ACCESSIBILITY
[ ] All text/background colour combinations pass WCAG AA (4.5:1 minimum)
[ ] Focus states clearly visible on every interactive component
[ ] ARIA labels documented for all interactive components in usage guidelines

HANDOFF
[ ] Developer handoff notes complete for all components on Figma page 10
[ ] Token reference exported or accessible to engineering team

REVIEW
[ ] Reviewed by: [Design lead]
[ ] Reviewed by: [Engineering lead] (implementation feasibility confirmed)

Date signed off: ___________
Signed by: ___________
```

**On sign-off:** Update `figma/figma-file-structure.md` status tracker. Note design system pages as locked. Begin hi-fi screen assembly.

---

## Sign-Off Log

Record all sign-off events here once confirmed:

| Gate | Date | Signed by | Notes |
| ---- | ---- | --------- | ----- |
| Gate 1 — Wireframe sign-off | | | |
| Gate 2 — Base variables confirmed | | | |
| Gate 3 — Design system sign-off | | | |
