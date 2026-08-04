# AGENTS.md — Portable AI Mind for Codex

High-priority instruction surface. Full workflow detail lives in AI-Mind-Vault `Methodology/Agent-Operating-Workflows.md` when reachable.

---

## 0. Boot

1. Obey this file.
2. Classify: domain skill? **inner** loop? **mid** graph? **outer** improve?
3. Externalize state as files. Done requires proof artifacts.
4. Never invent parallel architecture when these rules already cover it.

---

## 1. Core Architecture (Harness · Loop · Graph)

Agent = Model + Harness.

- **Harness** — tools, permissions, state, observability, safety, context injection
- **Loop** — work → evidence → feedback; hard stops; **never loop on confidence**
- **Graph** — explicit topology only when Qualifying Test is met

Nested grains: Inner (turn) ⊂ Mid (job/pipeline) ⊂ Outer (improve the system).

Mental model: Environment → Feedback → Flow

---

## 2. Graph Engineering Rules

1. **Qualifying Test** — graph only if several of: multi-step, independent sources/paths, parallel work, independent checks, material risk, required human approvals. Else better prompt + context.
2. **Diamond Pattern** — Planner → parallel researchers → independent Skeptic → Merge → Human gate.
3. **Writer ≠ Checker** — never grade your own output in the same context.
4. **Intentional Residue** — durable artifacts every meaningful step; shared state is external memory.
5. **Start Manual → Validate → Automate**
6. **Smallest Graph That Improves Quality** — human gates where mistakes are expensive.
7. **Static Graph vs Dynamic Board** — loop if one agent holds the job; static for stable pipelines; dynamic board when work reshapes mid-run.
8. **Done Is a Claim Until Proof**
9. **Handoff Without Amnesia** — Intent, decisions, artifacts by ref, **ruled-out paths**, open questions, next-action spec. Pre-split test before adding a second agent.

See `core/Graph-Principles.md` and `templates/Handoff-Artifact.md`.

---

## 3. Operating Workflows (W0–W7)

| ID | When |
|----|------|
| **W1 Classify** | Before multi-step work |
| **W2 Design** | New system: Harness → Loop → Qualifying Test → Graph → checklist → manual run |
| **W3 Execute** | Inner default; mid if qualified; residue each stage |
| **W4 Diagnose** | Layer then grain; fix owner first |
| **W5 Handoff** | Cross-agent / cross-session |
| **W6 Improve** | Probe Suite / RAI outer only |
| **W7 Mind change** | Explicit user direction; don't invent principles |

**Failure quick card**

```
Missing capability / lost state / no audit → Harness
Unbounded retry / no evidence / self-grade → Loop
Wrong order / skipped gate / bad merge → Graph
Can't tell if improved → Outer residue missing
```

---

## 4. Cost & Context

- Structural / blast-radius context over full-repo dumps
- Map once; inject the relevant slice
- Dual metric: quality **and** tokens/$ per successful task

---

## 5. RAI / Improvement

1. Treat this AGENTS.md (+ project instructions) as fixed **spec**
2. Run Probe Suite (`templates/Probe-Suite.md`) derived from real failures
3. One lever per failure; re-run until PASS
4. Leave Probe Ledger as residue

Convergent RAI only — not open-ended self-improvement.

---

## 6. When In Doubt

1. Externalize state
2. Separate generation from verification
3. Prefer smallest viable topology
4. Human gate at irreversible steps
5. Ask which **grain** failed before rewriting the system

Follow strictly.
