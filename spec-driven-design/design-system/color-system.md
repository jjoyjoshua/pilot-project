# Design System — Color System

Nothing in a hi-fi screen is a raw value. Every colour flows from a named token.

---

## Layer 1 — Primitive Tokens
Raw values. Never used directly in components.

| Token | Hex |
|-------|-----|
| blue-50 | #EFF6FF |
| blue-100 | #DBEAFE |
| blue-200 | #BFDBFE |
| blue-400 | #60A5FA |
| blue-600 | #2563EB |
| blue-800 | #1E40AF |
| blue-900 | #1E3A8A |
| neutral-0 | #FFFFFF |
| neutral-50 | #F9FAFB |
| neutral-100 | #F3F4F6 |
| neutral-200 | #E5E7EB |
| neutral-400 | #9CA3AF |
| neutral-600 | #4B5563 |
| neutral-900 | #111827 |
<!-- Add full brand color scale, semantic colors (red, green, amber) here -->

---

## Layer 2 — Semantic Tokens
Reference primitive tokens. Used in components.

| Token | References |
|-------|------------|
| color/action/primary | blue-600 |
| color/action/primary-hover | blue-800 |
| color/action/primary-text | neutral-0 |
| color/action/secondary | neutral-100 |
| color/action/secondary-text | neutral-900 |
| color/feedback/error | red-600 |
| color/feedback/error-surface | red-50 |
| color/feedback/success | green-600 |
| color/feedback/success-surface | green-50 |
| color/feedback/warning | amber-500 |
| color/feedback/warning-surface | amber-50 |
| color/surface/page | neutral-50 |
| color/surface/card | neutral-0 |
| color/surface/overlay | neutral-100 |
| color/text/primary | neutral-900 |
| color/text/secondary | neutral-600 |
| color/text/tertiary | neutral-400 |
| color/text/inverse | neutral-0 |
| color/text/error | red-700 |
| color/text/link | blue-600 |
| color/border/default | neutral-200 |
| color/border/strong | neutral-400 |
| color/border/focus | blue-600 |

---

## Layer 3 — Component Tokens
Reference semantic tokens. Applied to component properties.

| Token | References |
|-------|------------|
| button/primary/background | color/action/primary |
| button/primary/background-hover | color/action/primary-hover |
| button/primary/label | color/action/primary-text |
| button/primary/border | transparent |
| input/background | color/surface/card |
| input/border-default | color/border/default |
| input/border-focus | color/border/focus |
| input/border-error | color/feedback/error |
| input/text | color/text/primary |
| input/placeholder | color/text/tertiary |

## Figma Setup
Set up as Variable collections: `primitive`, `semantic`, `component`. Use variable aliasing to reference layer to layer.
