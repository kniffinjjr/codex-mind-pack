# codex-mind-pack

**Portable AI Mind pack optimized for OpenAI Codex** (and Claude Code / other agents).

This repository packages the durable core of our AI Mind (Harness · Loop · Graph architecture + Graph Engineering principles) in a form that Codex can reliably follow even without access to private vaults or full GitHub context.

Clone it tomorrow on your work computer and use it as working context or the source of your `AGENTS.md`.

## Quick Start (Tomorrow on Work Computer)

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
   cp AGENTS.md /path/to/your/work-repo/
   # or work inside this directory for mind-aligned sessions
   ```

3. **Context injection**: In Codex sessions, `@` mention files from this pack (especially `AGENTS.md` and `core/`).

## What Codex Gets From This Pack

- **AGENTS.md** — high-priority durable instructions Codex is trained to follow.
- Core Harness · Loop · Graph mental model.
- Concrete Graph Engineering rules (Qualifying Test, Diamond Pattern, Writer ≠ Checker, Intentional Residue).
- Ready templates for planning and residual state.

## Structure

```
codex-mind-pack/
├── AGENTS.md                          # Primary instruction file for agents
├── README.md                          # This file
├── LICENSE
├── core/
│   ├── Harness-Loop-Graph.md          # Condensed architecture
│   └── Graph-Principles.md            # Operational rules (Qualifying Test, Diamond, Residue...)
├── templates/
│   ├── Diamond-Research.md
│   ├── Graph-Engineering-Template.md
│   └── Residue-Structure.md
└── examples/
    └── (future worked examples)
```

## Recommended Codex Workflow

1. Start complex tasks in **plan mode** and write the topology (or Diamond) as files first.
2. Force **intentional residue**: every meaningful step writes durable artifacts (PLAN.md, EVIDENCE.md, STATUS.md, etc.).
3. Keep **Writer ≠ Checker**: never let the same context grade its own output.
4. Use the Qualifying Test before spinning up multi-node graphs.
5. Put human gates only where risk is asymmetric.

## Relationship to Full AI-Mind-Vault

This is the *portable, Codex-facing surface* of the private `AI-Mind-Vault`. The vault remains the source of truth for deeper concepts, projects, skills, and review process. Keep this pack in sync when major principles change.

Created 2026-08-03 / 2026-08-04 for reliable agentic work.
