# Phase 6 — Concept Validation

> **Instruction file for Claude Code.**
> Execute this phase after Phase 5 is complete. Output goes to `[project]-ux/research/06-concept-validation.md`.

---

## Purpose

Test core concepts and flows with real users before investing in detailed wireframes. Catch structural problems when they are still just sketches — not after hours of design work.

---

## Inputs

- `[project]-ux/00-master-spec.md` — assumptions list
- `[project]-ux/research/01-discovery.md` — unvalidated assumptions
- `[project]-ux/research/02-user-research.md` — assumption audit results
- `[project]-ux/research/04-ia.md` — navigation model, critical paths
- `[project]-ux/research/05-ux-strategy.md` — design principles, UX brief
- Any concept sketches or low-fidelity prototypes shared by the user

---

## Execution Steps

### Step 1 — Build the assumption map

Take all assumptions from Phases 1 and 2. Plot each by two dimensions:

- **Criticality:** How much does the design break if this assumption is wrong?
- **Confidence:** How much evidence do we have that this assumption is true?

Quadrants:

- High criticality + low confidence = **Test first — these are risky**
- High criticality + high confidence = **Validate, lower priority**
- Low criticality + any confidence = **Monitor — don't spend time testing now**

### Step 2 — Prepare concept testing plan

For each high-criticality, low-confidence assumption, define a concept to test that will prove or disprove it. Each concept should be a rough sketch or described scenario — no colour, no detail.

Testing session format:

- Duration: 30–45 minutes
- Materials: Paper sketches or rough Figma frames (no colour, no detail)
- Participants: 3–5 users per concept direction
- Record: What participants say, what they do, what confuses them

### Step 3 — Document results per concept

For each concept tested, capture: what worked, what didn't, and the go/no-go decision.

Go/no-go rules:

- ✅ GO: Core concept validated. List any changes required before wireframing.
- ⚠ GO WITH CHANGES: Concept works but needs significant modification. List specific changes.
- ❌ NO-GO: Concept rejected. State what to try instead.

### Step 4 — Carry forward open questions

Any questions that concept validation raised but did not answer get carried into the wireframe phase as open questions on the relevant screen specs.

### Step 5 — Write the output file

If no concept validation has been conducted yet, document the plan (which assumptions to test, what concepts to try) and mark each as `[PENDING — test before wireframing begins]`.

---

## Output Template

````markdown
# Phase 6 — Concept Validation
Product: [product name]
Date: [date]

---

## Assumption Map

### High criticality + low confidence — Test first

| Assumption ID | Assumption | Why risky |
| ------------- | ---------- | --------- |
| ASSUMPTION-005 | [assumption] | [what breaks if wrong] |

### High criticality + high confidence — Validate

| Assumption ID | Assumption | Evidence for confidence |
| ------------- | ---------- | ----------------------- |
| ASSUMPTION-002 | [assumption] | [evidence] |

### Low criticality — Monitor only

| Assumption ID | Assumption |
| ------------- | ---------- |
| ASSUMPTION-009 | [assumption] |

---

## Concept Testing Plan

### Concept A — [Concept name]

**What it tests:** ASSUMPTION-[ID] — [assumption being tested]
**Format:** [paper sketch / rough Figma / described scenario]
**Scenario to give participants:**
> "[The scenario script to read aloud at the start of the session]"

**Key questions to probe:**
- [question 1]
- [question 2]
- [question 3]

---

## Concept Testing Results

### Concept A — [Concept name]

**Tested with:** P01, P03, P05, P07, P08
**Status:** ✅ GO / ⚠ GO WITH CHANGES / ❌ NO-GO

#### What worked
- [finding 1] — observed in [N]/[N] participants
- [finding 2]

#### What didn't work
- [finding 1] — [N]/[N] participants [description of problem]
- [finding 2]

#### Desirability words selected by participants
[List words chosen from: Overwhelming / Clear / Complicated / Familiar / Powerful / Simple / Confusing / Trustworthy]

#### Decision
[✅ GO / ⚠ GO WITH CHANGES / ❌ NO-GO] — [one sentence justification]

**Changes required before wireframing:**
1. [change 1]
2. [change 2]

---

### Concept B — [Concept name]
[same structure]

---

## Assumption Audit — Final Status

| Assumption ID | Assumption | Final status | Evidence |
| ------------- | ---------- | ------------ | -------- |
| ASSUMPTION-001 | [assumption] | ✅ Validated | [evidence from testing] |
| ASSUMPTION-005 | [assumption] | ❌ Invalidated | [evidence] |
| ASSUMPTION-008 | [assumption] | ⚠ Unclear — carry to wireframe | [evidence] |

---

## Open Questions Carried into Wireframing

| Question | Related screens | Needs answer from |
| -------- | --------------- | ----------------- |
| [question] | SCR-0X, SCR-0Y | [product owner / engineering / design] |

---

## Wireframe Readiness

- [ ] All high-criticality assumptions tested or accepted with known risk
- [ ] All NO-GO concepts have a replacement direction
- [ ] All GO WITH CHANGES concepts have a clear change list
- [ ] Open questions documented on relevant screen spec files
- [ ] UX brief and design principles confirmed as unchanged after validation
````
