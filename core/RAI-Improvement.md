# Recursive Auto-Improvement (RAI) — Practical Subset for Codex / GPT Agents

**Source pattern:** Convergent improvement against a fixed written spec (mapped from production agent practice).

## Core Distinction

- **RSI** (Recursive Self-Improvement): System improves *itself*; gains compound into further improvement ability → divergent.
- **RAI** (Recursive Auto-Improvement): A coding agent improves a *target* agent (or instruction set) against a **fixed written spec** using probes → convergent. Preferred for production reliability.

We adopt **RAI**.

## The Practical Loop (Codex-ready)

1. Treat `AGENTS.md` + core files as the written **spec**.
2. Derive or load probes (Golden / Edge / Tool-Residue / Handoff / Adversarial) with one-line expected behavior.
3. Run the probes against the current agent behavior or proposed change.
4. Review outcomes + any available traces/logs.
5. Make small targeted edits (usually to instructions or supporting files).
6. Re-run only the failures (plus spot-checks) until every probe passes.
7. Record results in a Probe Ledger (intentional residue).

Preferred mode: batch the suite overnight or at the end of a work session.

## Harness Requirements (for the loop to close)

- Editable instructions / files (this pack)
- Ability for the coding agent to invoke / simulate the target behavior
- Residue surface for the Probe Ledger and before/after notes
- (Ideal later) full logs and usage data for mining new probes

## Mapping

- **Loop**: Improvement / verification loop with evidence-based stopping rule.
- **Harness**: Provides the editable surface + observability + residue.
- **Graph**: Usually a simple cycle. Expand only if Qualifying Test is met.
- **Eval Engineering**: Probes *are* the control-flow-changing evals. Failures become permanent probes.

## How to Use with This Pack

1. Load `AGENTS.md` + `templates/Probe-Suite.md`.
2. Run the starter probes (or a subset) against any proposed change to the mind or a new agent.
3. Update the LEDGER section with before/after results.
4. Only consider the change “done” when every relevant probe passes.

See `templates/Probe-Suite.md` for the concrete starter suite and `templates/RAI-Loop.md` for the step-by-step.
