# Harness · Loop · Graph Architecture (Condensed)

**Purpose:** Reliable production AI agents by correctly distinguishing the three layers.

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

## Expensive Mistakes to Avoid
1. Graph before understanding the work
2. Same model writes and grades without safeguards
3. “Keep trying” as a loop
4. Harness as dumping ground
5. Blaming the model for orchestration failures
