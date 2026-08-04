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
- Handoff envelopes (for multi-agent work)

Shared state is the external memory. Residue compounds: the next similar run starts smarter.

## 5. Start Manual, Validate Topology, Then Automate
Draw the jobs and arrows first (whiteboard, Excalidraw, or markdown). Run it fully by hand once with separate chats/files. Only then move to orchestration.

## 6. Smallest Graph That Actually Improves Quality
More agents ≠ better. Coordination cost and noise rise quickly. Put the human decision where a mistake is expensive (capital, irreversible actions, public output, high-stakes recommendations).

## 7. Static Graph vs Dynamic Board
- **Static graph** (LangGraph-style): flowchart authored up front. Possible paths are mostly predefined; routing can still be runtime.
- **Dynamic board**: shared task board agents read/write. Agents claim work, add new tasks mid-run, drop finished ones. The graph rewrites itself as reality changes.

Use a **loop** when one agent can hold the whole job.
Use a **static graph** for stable, predictable pipelines.
Use a **dynamic board** when work branches, finishing one task creates or cancels others, or the team should grow/shrink with the work.

## 8. Done Is a Claim Until Proof
Marking a task done is not proof. Re-run tests / checks. Status rows without evidence drift. Bookkeeping (who claimed what) must not live only in an agent’s head.

## 9. Handoff Without Amnesia
When work crosses agent boundaries, pass a structured **Handoff Artifact** (see `templates/Handoff-Artifact.md`):
- Intent
- Decisions + rationale
- Artifacts by reference
- Ruled-out / rejected paths (negative space)
- Open questions
- Confidence tags

Pre-split test: if the second agent needs most of the first agent’s full context to continue, do not split yet.
