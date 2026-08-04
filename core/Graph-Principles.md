# Graph Engineering Principles (Operational)

These rules are first-class and must be followed for non-trivial multi-step work.

## 1. Qualifying Test
Reserve graphs for work that has several of:
- Multiple steps
- Multiple independent sources or paths
- Parallelizable work
- Need for checks / grading / verification
- Material risk if wrong
- Required human approvals

If none apply → better prompt + better context is superior (and cheaper).

## 2. Diamond Pattern (Default Research / Analysis Shape)
```
Planner
  ↓
Parallel Specialized Researchers (different lenses)
  ↓
Independent Skeptic (attacks the evidence)
  ↓
Merge of what survives
  ↓
Human Gate
```

This forces evidence over vibes and is the first pattern most people should learn.

## 3. Writer ≠ Checker
Structural separation of concerns. Never let the same model (or the same context window) grade its own output. Self-evaluation systematically inflates confidence.

## 4. Intentional Residue / Externalized State
Every node should leave durable artifacts:
- PLAN.md / topology diagrams
- EVIDENCE.md or scored tables
- STATUS.md / progress logs
- Decision records

Shared state is the external memory. Residue compounds: the next similar run starts smarter.

## 5. Start Manual, Validate Topology, Then Automate
Draw the jobs and arrows first (whiteboard, Excalidraw, or markdown). Run it fully by hand once with separate chats/files. Only then move to orchestration.

## 6. Smallest Graph That Actually Improves Quality
More agents ≠ better. Coordination cost and noise rise quickly. Put the human decision where a mistake is expensive (capital, irreversible actions, public output, high-stakes recommendations).
