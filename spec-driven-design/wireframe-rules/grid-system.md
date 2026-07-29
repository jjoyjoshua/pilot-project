# Wireframe Rules — Grid System

> **Standard document.** Copy this file verbatim into `[project]-ux/wireframe-rules/grid-system.md` at pipeline start.
> When generating wireframe frames in Figma, apply the grid defined here to every top-level frame before placing any content.

---

## How Claude Code applies this

1. When creating a wireframe frame in Figma, set the Layout Grid to match the breakpoint in scope
2. Apply the grid **before** placing any component — layout grid first, content second
3. Never place content outside the grid columns
4. Use margin values to constrain the outermost auto layout wrapper
5. Copy this file to the project folder unchanged — grid values are fixed standards, not per-project decisions

---

## Desktop Grid

| Property | Value |
| -------- | ----- |
| Columns | 12 |
| Gutter | 24px |
| Margin | 40px (left and right) |
| Max content width | 1280px |
| Frame width | 1440px (standard desktop canvas) |

## Tablet Grid (include if tablet is in scope)

| Property | Value |
| -------- | ----- |
| Columns | 8 |
| Gutter | 20px |
| Margin | 24px |
| Frame width | 768px |

## Mobile Grid (include if mobile is in scope)

| Property | Value |
| -------- | ----- |
| Columns | 4 |
| Gutter | 16px |
| Margin | 16px |
| Frame width | 390px |

---

## Figma Setup Instructions

- Create as **Layout Grid Styles** in the Figma local styles panel
- Name them: `Grid / Desktop 12-col`, `Grid / Tablet 8-col`, `Grid / Mobile 4-col`
- Apply the appropriate grid style to every top-level wireframe frame
- The grid must be visible (not hidden) during wireframe review for sign-off

---

## Rules — No Exceptions

- Every top-level wireframe frame has the grid applied before content is placed
- No element sits outside the grid columns intentionally — flag any that do as a layout issue
- Content width is constrained by the grid margin, not by arbitrary padding on the content itself
- The sidebar nav (if present) sits in columns 1–2; the main content area in columns 3–12
