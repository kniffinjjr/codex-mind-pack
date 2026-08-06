# Eval Engineering (Portable)

**Definition:** evaluation that **changes control flow** (what runs next, what is promoted, what is blocked) — not scores that only decorate a dashboard.

## Principles

1. **Evidence over confidence** — success criteria are external (tests, schema, citations, human sign-off).
2. **Writer ≠ grader** — separate contexts or use deterministic checks.
3. **Traces are first-class** — replay real failures; attribute improvement to a specific change (prompt, tool, loop, edge).
4. **No evals, no production.**
5. **Regression from real failures** — production bugs become suite cases.
6. **Dual metric** — quality **and** cost (tokens / $) per correct outcome; accuracy alone hides 10–50× bills.
7. **No process porn** — gates that don’t change a real edge (or that agents can edit/close themselves) become reward hacks.
8. **Coding agents are cost-constrained by default** — prefer structural/minimal context over full-repo reread.

## RAI (convergent)

Preferred production improvement pattern:

1. Derive categorized probes (Golden / Edge / Tool Selection / Adversarial / Handoff) from a fixed written spec + real failures.
2. Run probes against the live target agent.
3. Inspect full trajectory logs.
4. One small lever per failure (prompt, tool, policy).
5. Re-run until every probe passes; leave Probe Ledger as residue.

Failures become permanent probes. We adopt **convergent RAI** toward a fixed spec — not open-ended RSI.

See `core/RAI-Improvement.md` and `templates/Probe-Suite.md`.
