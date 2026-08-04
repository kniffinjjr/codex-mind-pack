# AGENTS.md — Portable AI Mind for Codex

## Core Architecture (Harness · Loop · Graph)

Agent = Model + Harness.

Stack as systems mature:
- **Harness** — tools, permissions, state, observability, safety, context injection (the machinery around the model)
- **Loop** — repeated work-and-evidence cycle with clear goal, stopping rules, and feedback (evidence > confidence)
- **Graph** — explicit workflow topology (nodes, edges, state) only when needed

Mental model: Environment → Feedback → Flow

## Graph Engineering Rules (Committed Principles)

1. **Qualifying Test**  
   Use a graph only when the work has several of: multiple steps, independent sources/paths that can run in parallel, need for checks/grading, material risk if wrong, or required human approvals.  
   Otherwise use a better prompt + better context.

2. **Diamond Pattern (default research / analysis shape)**  
   Planner → parallel specialized researchers (different lenses) → independent Skeptic that attacks the evidence → Merge of what survives → Human gate.

3. **Writer ≠ Checker**  
   Never let the same model (or same context) grade its own output. Structural separation of generation from verification is mandatory for high-stakes work.

4. **Intentional Residue / Externalized State**  
   Every node/step should leave durable artifacts (files, notes, scored tables, evidence logs, handoff envelopes). Shared state lives in the filesystem, not only in chat. Residue compounds across runs.

5. **Start Manual → Validate Topology → Then Automate**  
   Draw the jobs and arrows first. Run by hand once. Only then orchestrate.

6. **Smallest Graph That Improves Quality**  
   More agents ≠ better. Put human decision points only where mistakes are expensive.

7. **Static Graph vs Dynamic Board**  
   Loop when one agent can hold the job. Static graph for stable pipelines. Dynamic shared board when work discovers new tasks and the team should reshape mid-run.

8. **Done Is a Claim Until Proof**  
   Status without evidence is not done. Re-run checks. Do not trust bookkeeping that lives only in an agent’s head.

9. **Handoff Without Amnesia**  
   Multi-agent boundaries require a structured Handoff Artifact (intent, decisions, artifacts by reference, **ruled-out paths**, open questions). See `templates/Handoff-Artifact.md`.

## Operating Rules

- Prefer evidence over confidence or self-report.
- Externalize plans, decisions, verification results, and status as files.
- For coding tasks: map structure once, inject only blast-radius / relevant context (see cost-efficient context guidance).
- Done criteria: acceptance criteria met + verification evidence exists + residue written.

## Improvement Discipline (RAI)

Before deploying or significantly changing agent behavior:

1. Treat this AGENTS.md (and project instructions) as the fixed written **spec**.
2. Run the Probe Suite in `templates/Probe-Suite.md` (or an extended suite derived from real failures).
3. Fix failures with small targeted edits.
4. Re-run until every probe passes.
5. Leave the Probe Ledger as intentional residue.

Prefer **convergent** Recursive Auto-Improvement (RAI) toward the written spec. Do not default to open-ended divergent self-improvement.

See `core/RAI-Improvement.md` and `templates/RAI-Loop.md`.

## When In Doubt

1. Externalize state.
2. Separate generation from verification.
3. Prefer the smallest viable topology.
4. Ask for human gate at irreversible steps.

This file is the high-priority instruction surface for Codex and compatible agents. Follow it strictly.
