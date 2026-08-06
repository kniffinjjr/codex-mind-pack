# codex-mind-pack

**Portable AI Mind pack optimized for OpenAI Codex and GPT-based agents** (also usable with Claude Code and other coding agents).

This repository is the **public, work-safe surface** of the private AI-Mind-Vault. It keeps the same Harness · Loop · Graph architecture, Nested Cycles, RAI discipline, and Probe Suite so personal research and work projects stay aligned, while cleanly separating Grok-native personal surfaces from Codex/GPT work surfaces.

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

3. **Context injection**: In Codex / GPT sessions, `@` mention files from this pack (especially `AGENTS.md`, `core/`, `templates/Probe-Suite.md`, and any needed `personalities/` pack).

## What This Pack Provides

- **AGENTS.md** — high-priority durable instructions agents are trained to follow.
- Core Harness · Loop · Graph mental model + **Nested Cycles** (Inner ⊂ Mid ⊂ Outer).
- **Eval Engineering** — score that changes the next edge; convergent RAI.
- Concrete Graph Engineering rules (Qualifying Test, Diamond Pattern, Writer ≠ Checker, Intentional Residue).
- **Diagram Principles** — geometry-first rules so architecture visuals stay clear (nested vs stack vs spine vs loop).
- **RAI Improvement Loop** + starter **Probe Suite** (including handoff / negative-space probes).
- Ready templates for planning, residue, and handoffs.
- **Specialist personalities** (optional ≤4000-char packs) adapted for Codex.

## Structure

```
codex-mind-pack/
├── AGENTS.md                          # Primary instruction file
├── README.md                          # This file
├── LICENSE
├── core/
│   ├── Harness-Loop-Graph.md          # Architecture overview
│   ├── Nested-Cycles.md               # Grain model + promotion + residue
│   ├── Graph-Principles.md
│   ├── Eval-Engineering.md            # Control-flow eval + RAI
│   ├── Diagram-Principles.md          # Architecture visual geometry
│   └── RAI-Improvement.md
├── templates/
│   ├── Diamond-Research.md
│   ├── Graph-Engineering-Template.md
│   ├── Residue-Structure.md
│   ├── Handoff-Artifact.md
│   ├── RAI-Loop.md
│   └── Probe-Suite.md
└── personalities/
    ├── README.md
    └── … specialist packs
```

## Purpose: Personal Research vs Work Projects

- **Private AI-Mind-Vault** = personal research, Grok-native surfaces, full methodology, project overviews, review process, diagram-design skill.
- **This pack** = portable Codex / GPT surface intended for work computers, shared repos, and any environment where Grok branding or personal residue should stay out.

Architecture stays identical so the two surfaces remain aligned. Domain skills and Grok-specific catalogs stay in the Vault; the pack carries only the durable core + neutral specialist packs.

## Recommended Codex / GPT Workflow

1. Start complex tasks in **plan mode** and write the topology (or Diamond) as files first.
2. Force **intentional residue**: every meaningful step writes durable artifacts.
3. Keep **Writer ≠ Checker**.
4. Use the Qualifying Test before multi-node graphs.
5. Put human gates only where risk is asymmetric.
6. **Before deploy**: run the Probe Suite via the RAI Loop and leave the LEDGER as residue.
7. Optionally load one personality pack for domain depth; it never overrides AGENTS.md.

## Regular Update Policy

- **Last synced from AI-Mind-Vault:** 2026-08-06 (afternoon — Nested-Cycles, Eval, Diagram Principles)
- **Trigger a re-sync when:** AGENTS.md, Nested-Cycles, Graph Principles, RAI, Probe Suite, Handoff Spec, Eval Engineering, or the specialist personality set change in the private vault.
- **Owner action:** Ask GrokRarian (or any agent with vault access) to “sync codex-mind-pack” after those controlling documents are updated and approved.
- **This pack never auto-pulls.** All updates are intentional pushes.

## Changelog (pack)

### 2026-08-06 (afternoon)
- Added `core/Nested-Cycles.md` (full grain model, promotion, residue boundaries).
- Added `core/Eval-Engineering.md` (control-flow eval + convergent RAI).
- Added `core/Diagram-Principles.md` (geometry-first architecture visuals).
- AGENTS.md points at Nested-Cycles, Eval, and Diagram Principles.

### 2026-08-06 (earlier)
- Added `personalities/` with 8 GPT/Codex-adapted specialist packs.
- Clarified pack purpose: separate personal research surface from work projects while keeping architecture aligned.
- AGENTS.md gains pointer to optional personalities.
- Full sync of portable rules (Nested Cycles summary, W table, cost policy, offline rules).
- Probe Suite expanded with handoff probes; Handoff template tightened.

Created 2026-08-03 / 2026-08-04. Maintained as the reliable GPT/Codex surface of the AI Mind.
