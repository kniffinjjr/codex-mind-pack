# Handoff Artifact Spec

**Purpose:** Prevent handoff amnesia. Pass evidence, not just conclusions.

A prose summary of what Agent A learned is not usable evidence for Agent B. The only durable handoff is structured residue that carries artifacts and the negative space (what was tried and rejected).

## Pre-split test (cheapest fix)

Before creating a second agent, ask:

> What does the second agent actually need to have seen?

If the answer is most of what the first agent saw → **do not split**. You have one agent + expensive amnesia.

## Required Fields

```markdown
## Handoff — [Task / Stage ID]

### 1. Original Goal / Intent
[What the upstream agent was trying to achieve — do not silently reinterpret]

### 2. Decisions Made + Rationale
- Decision: …
  Why: …

### 3. Artifacts (by reference preferred)
- path/or/id — short description
- captured response / schema / file — …

### 4. Ruled-Out / Rejected Approaches (Negative Space) — REQUIRED
- Approach tried: …
  Result / error: …
  Why ruled out: …

### 5. Open Questions / Blockers
- …

### 6. Confidence + Provenance
- Finding X — confidence: high/med/low — source: tool output | inference | inherited

### 7. Next-Action Guidance (written as a *spec for the receiving agent*)
[What the next agent should do first, what it must not re-do, and what evidence it already has]
```

## Operating Rules

1. **Prefer artifacts by reference** over large inline content. Point to files, schemas, captured responses, or IDs in shared state.
2. **Negative space is mandatory.** Explicitly record what failed or was ruled out. This is the part that stops the next agent from re-paying the same cost.
3. **Write for the next agent, not a human.** A report optimizes for narrative; a handoff optimizes for actionability and completeness of evidence.
4. **Pre-split test.** Before introducing a second agent, ask: “What does the second agent actually need to have seen?” If the answer is most of what the first saw, do not split.
5. Prefer shared durable state (filesystem, typed graph state, checkpointer) + a compact structured envelope over one-shot prose handoffs.

## Relation to Core Principles

- Direct application of **Intentional Residue / Externalized State**.
- Supports **Writer ≠ Checker** (evidence must travel with the conclusion).
- Aligns with Graph Engineering: only split when the Qualifying Test is met *and* the handoff can carry the necessary residue.
