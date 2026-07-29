# Wireframe Rules — Lo-Fi Component Set

> **Standard document.** Copy this file verbatim into `[project]-ux/wireframe-rules/component-set.md` at pipeline start.
> Build all components listed here in Figma **before** starting any screen wireframe.

---

## How Claude Code applies this

1. Read this file before generating any wireframe frames
2. Verify the lo-fi component set exists in Figma on page `07 · Wireframe system`
3. If a component is missing, build it first — then use it in the wireframe
4. Never draw a raw rectangle or shape on a wireframe screen — place a component from this set
5. If a needed component is not in this list, flag it and add it to the inventory before using it

---

## Auto Layout — Three Modes

Apply the correct mode to every container. No manually positioned elements anywhere.

| Mode | Behaviour | Use for |
| ---- | --------- | ------- |
| **FILL** | Stretches to fill the parent container | Content that grows with screen width — page wrappers, sections, rows |
| **HUG** | Wraps tightly around its children | Buttons, tags, labels, cards with variable content length |
| **FIXED** | Explicit pixel dimensions, does not resize | Icons, images, avatar circles, elements with a defined size |

## Standard Nesting Pattern

```text
Page frame (FILL — full viewport width)
  └── Layout wrapper (FILL — max-width constrained to grid)
        └── Section (FILL — full available width)
              └── Card (HUG — wraps content)
                    ├── Card header (FILL — full card width)
                    ├── Card body (FILL — full card width)
                    └── Card footer (HUG — wraps action buttons)
```

---

## Component Build Order

Build in this order — containers before their contents.

### 1 — Layout primitives (build first)

- [ ] Divider — horizontal
- [ ] Divider — vertical
- [ ] Spacer — fixed height (for use as explicit spacing blocks where needed)

### 2 — Navigation

- [ ] Nav item — default state
- [ ] Nav item — active state
- [ ] Nav item — hover state
- [ ] Nav bar — desktop sidebar (composed of nav items)
- [ ] Nav bar — top bar

### 3 — Form controls

- [ ] Input — default / focus / error / disabled (4 variants)
- [ ] Textarea — default / focus (2 variants)
- [ ] Dropdown — closed / open (2 variants)
- [ ] Checkbox — unchecked / checked / indeterminate (3 variants)
- [ ] Radio — unselected / selected (2 variants)
- [ ] Toggle — off / on (2 variants)

### 4 — Actions

- [ ] Button — primary / secondary / ghost / destructive × sm / md / lg (12 variants)
- [ ] Icon button — default / hover (2 variants)

### 5 — Data display

- [ ] Badge — neutral / positive / warning / error (4 variants)
- [ ] Tag — default / removable (2 variants)
- [ ] Avatar — initials / image / group (3 variants)
- [ ] Table header row
- [ ] Table data row
- [ ] Table empty state row

### 6 — Containers

- [ ] Card — default (no header)
- [ ] Card — with header
- [ ] Modal — small (480px wide)
- [ ] Modal — medium (640px wide)
- [ ] Modal — large (800px wide)
- [ ] Panel — left
- [ ] Panel — right

### 7 — Feedback

- [ ] Alert — info / success / warning / error (4 variants)
- [ ] Toast — info / success / warning / error (4 variants)
- [ ] Empty state — with CTA
- [ ] Empty state — without CTA
- [ ] Loading skeleton — block (full width, variable height)
- [ ] Spinner

---

## Component Rules — No Exceptions

1. Every component uses auto layout — no manually positioned child elements
2. Every padding, gap, and size value comes from the spacing variable scale in `spacing-variables.md`
3. Every colour comes from the greyscale variable set in `color-variables.md`
4. No brand colours, no raw hex values, no raw pixel numbers in any component property
5. All components live on Figma page `07 · Wireframe system` — not scattered across wireframe pages
6. Component names in Figma match the names in this document exactly

---

## Spec Annotation Component

Every wireframe frame must have this component placed to its right. Build it once, use it on every screen.

```text
┌────────────────────────────────────┐
│ SCREEN SPEC                        │
├────────────────────────────────────┤
│ Screen ID:     SCR-0X              │
│ Screen name:   [name]              │
├────────────────────────────────────┤
│ REQ-IDs:                           │
│   REQ-FUNC-001  [short label]      │
│   REQ-UX-001    [short label]      │
├────────────────────────────────────┤
│ Primary user:  [persona name]      │
│ Primary job:   [JTBD — one line]   │
├────────────────────────────────────┤
│ IA position:                       │
│   Root > [path]                    │
├────────────────────────────────────┤
│ Design principle:                  │
│   "[Principle name]"               │
├────────────────────────────────────┤
│ Open questions:                    │
│ [ ] [question]                     │
└────────────────────────────────────┘
```
