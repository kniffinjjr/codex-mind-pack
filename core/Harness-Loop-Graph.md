# Harness · Loop · Graph Architecture (Condensed)

**Purpose:** Reliable production AI agents by correctly distinguishing the three layers.

Mental model: **Environment → Feedback → Flow**

> **Scope note (2026-08-14):** The detailed Skill Execution Contract (bounds table, progress rule, anti-meta-loop, single-pass exit) lives **only** in the `harness-loop-graph` skill and applies **only while that skill is active**. Do not treat those hard stops as default behavior for ordinary turns, coding, or simple tasks. High-level principles below remain core.

## 1. Agent Harness Engineering
Everything outside the model: system/context, tools, memory/files, sandboxes, routing, permissions, logging, verification interfaces, observability.

Key insight: Remove the model from the diagram. Everything left is the harness.

## 2. Loop Engineering
Core: model → tools → observe → repeat.

Well-engineered loop anatomy:
1. Trigger
2. Goal (specific terminal state)
3. State & memory
4. Action policy
5. Evidence (tests, schema, citations, metrics, human review)
6. Feedback (compact + actionable)
7. Stopping rule (success, budget, timeout, escalate)

**Critical rule:** Do **not** loop on confidence. Loop on **evidence**.

## 3. Graph Engineering
Answers: which component may run next?

- Nodes: deterministic / LLM / specialist agent / human
- Edges: sequence, branch, parallel, join, cycle, interrupt
- State travels through the graph

Use graphs for branches, parallel work, approvals, recovery, multi-agent coordination. Skip when one agent + tools is enough.

## Nested Cycles (grains)

```
OUTER  (meta / improvement)
  RAI · ops review · probe suite batch
  └── evidence = Probe Ledger, metrics, residue diffs
        │
MID    (job / workflow)
  Graph stages or single qualified loop
  └── each node is an inner loop (or human gate)
        │
INNER  (agent turn)
  model → tools → observe → stop on evidence
  └── harness supplies tools, state, budgets, gates
```

Same seven loop fields at every grain. Declare grain on every filled loop: `Grain: inner | mid | outer`.

Promotion rules:
- Single inner loop → Mid graph only when Qualifying Test is met
- Mid → Dynamic board when work discovers/cancels tasks mid-run
- Ad-hoc mid → Outer RAI when a written spec + Probe Suite is needed

## How the layers nest
```
Harness
└── Graph (explicit topology)
    └── Loop(s)
        └── Core agent loop (model ↔ tools)
```

## Failure Diagnosis

| Symptom | Fix Layer |
|---------|-----------|
| Missing capability / cannot recover / loses state / unauditable | Harness |
| No success criteria / unbounded retry / “keep trying” | Loop |
| Wrong order / missing branches / no human gates | Graph |
| Cannot attribute improvement | Evaluation (cross-cutting) |

Always also ask: **which grain failed?** Do not rewrite outer because an inner loop lacked a stop rule.

## Expensive Mistakes to Avoid
1. Graph before understanding the work
2. Same model writes and grades without safeguards
3. “Keep trying” as a loop
4. Harness as dumping ground
5. Blaming the model for orchestration failures
6. **Meta-loops** — re-reading the same skill, restating the same plan, or retrying the same failed tool without new evidence
