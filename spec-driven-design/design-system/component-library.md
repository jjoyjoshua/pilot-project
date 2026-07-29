# Design System — Component Library

> **Instruction file for Claude Code.**
> Build components in tier order — atoms before composites. No component at a higher tier is built until all components at the tier below it are complete.
> Track build status by checking off each item as it is completed in Figma.

---

## How Claude Code applies this

1. Before building any component, confirm the base variables (color, typography, spacing) are signed off — see `sign-off.md § Gate 2`
2. Build tiers in strict order: Tier 1 → Tier 2 → Tier 3 → Tier 4
3. For each component, build the full variant matrix (all states × all sizes × all types)
4. No component uses a raw value — every property references a token from the design system
5. After all tiers are complete, present the Gate 2 sign-off checklist to the user

---

## Tier 1 — Atoms

No dependencies on other components. Build these first.

| Component | Variants | Status |
| --------- | -------- | ------ |
| Icon | All sizes: icon-xs / icon-sm / icon-md / icon-lg / icon-xl | [ ] |
| Avatar | Initials / Image / Group × sm / md / lg | [ ] |
| Badge | Neutral / Positive / Warning / Error × sm / md | [ ] |
| Tag | Default / Removable | [ ] |
| Divider | Horizontal / Vertical | [ ] |
| Spinner | sm / md / lg | [ ] |
| Skeleton | Inline / Block (full width, variable height) | [ ] |

---

## Tier 2 — Base Components

Use Tier 1 atoms. Do not build until all Tier 1 components are complete.

| Component | Variants | Status |
| --------- | -------- | ------ |
| Button | Type: primary / secondary / ghost / destructive × Size: sm / md / lg × State: default / hover / active / focus / disabled / loading × Icon: none / left / right / icon-only | [ ] |
| Input | Type: text / password / search × State: default / focus / error / disabled | [ ] |
| Textarea | State: default / focus / error / disabled | [ ] |
| Checkbox | State: unchecked / checked / indeterminate / disabled | [ ] |
| Radio | State: unselected / selected / disabled | [ ] |
| Toggle | State: off / on / disabled | [ ] |
| Select / Dropdown | State: closed / open / selected / disabled | [ ] |
| Tooltip | Position: top / bottom / left / right | [ ] |

### Button variant matrix (build all)

| | primary | secondary | ghost | destructive |
| -- | ------- | --------- | ----- | ----------- |
| default | ● | ● | ● | ● |
| hover | ● | ● | ● | ● |
| active | ● | ● | ● | ● |
| focus | ● | ● | ● | ● |
| disabled | ● | ● | ● | ● |
| loading | ● | ● | ● | ● |

× sizes: sm / md / lg
× icon: none / icon-left / icon-right / icon-only

**Total button variants: 96** — use Figma variant properties to manage this.

---

## Tier 3 — Composite Components

Use Tier 1 and Tier 2 components. Do not build until all Tier 2 components are complete.

| Component | Variants | Status |
| --------- | -------- | ------ |
| Form field | Wraps: label + input + helper text + error message × State: default / focus / error / disabled | [ ] |
| Card | Layout: default / with header / with footer / horizontal | [ ] |
| Modal | Size: small (480px) / medium (640px) / large (800px) × State: default / loading / confirm | [ ] |
| Alert / Banner | Type: info / success / warning / error × Dismissable: yes / no | [ ] |
| Toast | Type: info / success / warning / error × Position: top-right / bottom-right | [ ] |
| Navigation item | State: default / hover / active / disabled × Has icon: yes / no | [ ] |
| Navigation sidebar | State: expanded / collapsed × Breakpoint: desktop / tablet | [ ] |
| Table | Row type: header / data / selected / empty × Column: sortable / unsortable | [ ] |
| Data list item | State: default / hover / selected / disabled | [ ] |
| Pagination | State: first page / mid / last page × Page count: shown / hidden | [ ] |

---

## Tier 4 — Page Patterns

Use Tier 3 composites. Do not build until all Tier 3 components are complete.

| Component | Variants | Status |
| --------- | -------- | ------ |
| Page header | With: title only / title + subtitle / title + actions / breadcrumb | [ ] |
| Empty state | With CTA / Without CTA × Context: first use / zero results / error / no permission | [ ] |
| Error state | Type: 404 / 500 / network offline / permission denied | [ ] |
| Loading state | Type: full page skeleton / section skeleton / inline spinner | [ ] |
| Onboarding step | With: progress bar / step counter / illustration | [ ] |
| Settings section | With: section header + form fields + save/cancel actions | [ ] |

---

## Variant Naming Convention in Figma

All component variant properties must follow this naming exactly:

| Property name | Allowed values |
| ------------- | -------------- |
| Type | primary, secondary, ghost, destructive, info, success, warning, error |
| Size | xs, sm, md, lg, xl |
| State | default, hover, active, focus, disabled, loading, selected, error |
| Icon | none, left, right, icon-only |
| Position | top, bottom, left, right, top-right, bottom-right |
| Dismissable | true, false |

---

## Component Rules — No Exceptions

1. Every component property (fill, stroke, text, spacing) must reference a token — never a raw value
2. Component tokens reference semantic tokens — never primitive tokens directly
3. Every interactive component has all interaction states (default, hover, focus, active, disabled)
4. Focus states must be clearly visible — use `color/border/focus` ring with 2px offset
5. Components are built on Figma page `10 · Design system — Components`
6. Usage guidelines are documented below each component on the same page
