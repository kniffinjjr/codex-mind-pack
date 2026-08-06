# codex-mind-pack

**Portable AI Mind pack optimized for OpenAI Codex and GPT-based agents** (also usable with Claude Code and other coding agents).

This repository packages the durable core of the AI Mind (Harness · Loop · Graph architecture + Graph Engineering principles + RAI improvement discipline + Nested Cycles) in a form that Codex / GPT agents can reliably follow even without access to private vaults or full GitHub context.

Clone it and use it as working context or the source of your `AGENTS.md`.

## Quick Start

```bash
git clone https://github.com/kniffinjjr/codex-mind-pack.git
cd codex-mind-pack
```

Then choose one (or both):

1. **Global Codex instructions** (recommended for all projects):
   ```bash
   mkdir -p ~/.codex
   cp AGENTS.md ~/.codex/AGENTS.md
   ```

2. **Per-project** (put the whole pack or just AGENTS.md into the root of the work repo):
   ```bash
   cp AGENTS.md /path/to/your-work-repo/
   # or work inside this directory for mind-aligned sessions
   ```

3. **Context injection**: In Codex / GPT sessions, `@` mention files from this pack (especially `AGENTS.md`, `core/`, and `templates/Probe-Suite.md`).

## What This Pack Provides

- **AGENTS.md** — high-priority durable instructions agents are trained to follow.
- Core Harness · Loop · Graph mental model + Nested Cycles (Inner ⊂ Mid ⊂ Outer).
- Concrete Graph Engineering rules (Qualifying Test, Diamond Pattern, Writer ≠ Checker, Intentional Residue).
- **RAI Improvement Loop** + starter **Probe Suite** (including handoff / negative-space probes) so you can harden agents (or the pack itself) before deploy.
- Ready templates for planning, residue, and handoffs.

## Structure

```
codex-mind-pack/
├── AGENTS.md                          # Primary instruction file for agents
├── README.md                          # This file
├── LICENSE
├── core/
│   ├── Harness-Loop-Graph.md          # Condensed architecture + Nested Cycles
│   ├── Graph-Principles.md            # Operational rules
│   └── RAI-Improvement.md             # Convergent improvement loop
├── templates/
│   ├── Diamond-Research.md
│   ├── Graph-Engineering-Template.md
│   ├── Residue-Structure.md
│   ├── Handoff-Artifact.md
│   ├── RAI-Loop.md
│   └── Probe-Suite.md                 # Starter probes + LEDGER (incl. P11/P12)
└── examples/
    └── (future worked examples)
```

## Recommended Codex / GPT Workflow

1. Start complex tasks in **plan mode** and write the topology (or Diamond) as files first.
2. Force **intentional residue**: every meaningful step writes durable artifacts (PLAN.md, EVIDENCE.md, STATUS.md, etc.).
3. Keep **Writer ≠ Checker**: never let the same context grade its own output.
4. Use the Qualifying Test before spinning up multi-node graphs.
5. Put human gates only where risk is asymmetric.
6. **Before deploy**: run the Probe Suite (`templates/Probe-Suite.md`) via the RAI Loop and leave the LEDGER as residue.

## Relationship to Full AI-Mind-Vault

This is the *portable, Codex/GPT-facing surface* of the private AI-Mind-Vault. The vault remains the source of truth for deeper concepts, projects, skills, and the review process. Keep this pack in sync when major principles change.

**Naming policy (this pack only):** All agent/platform references use GPT / Codex framing. No Grok-prefixed agent names are carried into this public surface.

## Regular Update Policy

- **Last synced from AI-Mind-Vault:** 2026-08-06
- **Trigger a re-sync when:** AGENTS.md, Nested-Cycles, Graph Principles, RAI, Probe Suite, or Handoff Spec change in the private vault.
- **Owner action:** Ask GrokRarian (or any agent with vault access) to “sync codex-mind-pack” after those controlling documents are updated and approved.
- **This pack never auto-pulls.** All updates are intentional pushes so the portable surface stays deliberate and reviewable.

## Changelog (pack)

### 2026-08-06
- Full sync of portable rules from vault (Nested Cycles, full W table, cost policy, offline rules).
- GPT / Codex rebrand applied to all platform/agent references in this pack only.
- Probe Suite expanded with handoff / negative-space probes (P11, P12).
- Handoff template tightened; core files refreshed.
- Explicit regular-update policy added to README.

Created 2026-08-03 / 2026-08-04. Maintained as the reliable GPT/Codex surface of the AI Mind.
