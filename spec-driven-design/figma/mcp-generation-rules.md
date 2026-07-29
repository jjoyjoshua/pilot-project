# Figma MCP Generation Rules — Pilot Project

Rules for the Figma MCP to follow when generating frames. Apply without exception.

---

## When Screen Pages Are Created

Wireframe and mockup pages are **not** created in advance. They are generated only after:

1. PRDs are analysed in Phase 0 (Spec Consolidation)
2. The screen inventory is drafted in Phase 1 (Discovery)
3. The screen inventory is finalised in Phase 4 (Information Architecture)
4. The `screens/` folder and per-screen spec files are created and confirmed

At that point, one Figma wireframe page and one mockup page are created per confirmed SCR-ID.

---

## General Rules

1. **Components only** — Place components from the library. Never draw raw shapes on a screen.
2. **No raw values** — Never type a colour hex, spacing number, or font size directly. Every value flows from a variable or text style.
3. **Layout first** — Build the page layout (grid, sections, spacing) before placing components.
4. **Annotation carries forward** — Every screen frame keeps its spec annotation (REQ-IDs, persona, design principle).
5. **One source of truth** — All colours from `semantic` variable collection. All spacing from `spacing` collection. All type from Text Styles.

---

## Frame Naming Convention

```text
[Phase prefix] / [SCR-ID] · [Screen name] / [State]

Examples:
  WF / SCR-02 · Dashboard / Default
  WF / SCR-02 · Dashboard / Empty state
  HF / SCR-02 · Dashboard / Default
```

- `WF` = Wireframe
- `HF` = Hi-fi mockup

---

## Spec Annotation Panel

Place to the right of every wireframe and hi-fi frame. Use this structure:

```text
┌─────────────────────────────────┐
│ SCREEN SPEC                     │
├─────────────────────────────────┤
│ Screen ID:    SCR-0X            │
│ Screen name:  [name]            │
├─────────────────────────────────┤
│ REQ-IDs:                        │
│   REQ-FUNC-00X (description)    │
├─────────────────────────────────┤
│ Primary user: [persona]         │
│ Primary job:  [JTBD statement]  │
├─────────────────────────────────┤
│ IA position:                    │
│   Root > [path]                 │
├─────────────────────────────────┤
│ Design principle:               │
│   "[principle name]"            │
├─────────────────────────────────┤
│ Open questions:                 │
│ [ ] [question]                  │
└─────────────────────────────────┘
```

---

## Wireframe Generation Checklist (per screen)

- [ ] Grid applied (12-column desktop)
- [ ] Auto layout on all frames and containers
- [ ] All spacing from `spacing/` variable collection
- [ ] All colours from `wireframe/` color variable collection
- [ ] All components from lo-fi component set (Page: `07 · Wireframe system`)
- [ ] Spec annotation panel placed to the right
- [ ] All states for the screen are separate frames

---

## Hi-Fi Generation Checklist (per screen)

- [ ] Grid applied
- [ ] Auto layout on all frames and containers
- [ ] All colours from `semantic` variable collection
- [ ] All spacing from `spacing` variable collection
- [ ] All type from Text Styles
- [ ] All components from component library (Page: `10 · Design system — Components`)
- [ ] Component tokens referencing semantic tokens (not primitive tokens directly)
- [ ] Spec annotation panel placed to the right
- [ ] Dev handoff redline notes placed below the frame
- [ ] All states for the screen are separate frames

---

## Page Order (do not reorder)

1. `_Index`
2. `01 · Discovery`
3. `02 · User research`
4. `03 · Synthesis`
5. `04 · Information architecture`
6. `05 · UX strategy`
7. `06 · Concept validation`
8. `07 · Wireframe system`
9. `08 · Wireframes — [Screen name]` (one per screen, in SCR-ID order)
10. `09 · Design system — Foundations`
11. `10 · Design system — Components`
12. `11 · Mockups — [Screen name]` (one per screen, in SCR-ID order)
