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

4. **Active project work**: park it under `Projects/<slug>/` (see below). This pack does **not** ship real projects.

## What This Pack Provides

- **AGENTS.md** — high-priority durable instructions agents are trained to follow.
- Core Harness · Loop · Graph mental model + **Nested Cycles** (Inner ⊂ Mid ⊂ Outer).
- **Eval Engineering** — score that changes the next edge; convergent RAI.
- Concrete Graph Engineering rules (Qualifying Test, Diamond Pattern, Writer ≠ Checker, Intentional Residue).
- **Diagram Principles** — geometry-first rules so architecture visuals stay clear (nested vs stack vs spine vs loop).
- **RAI Improvement Loop** + starter **Probe Suite** (including handoff / negative-space probes).
- Ready templates for planning, residue, and handoffs.
- **Specialist personalities** (optional ≤4000-char packs) adapted for Codex.
- **Projects/** — directory path and templates only; Codex moves active work here.

## Structure

```
codex-mind-pack/
├── AGENTS.md                          # Primary instruction file
├── README.md                          # This file
├── LICENSE
├── core/
│   ├── Harness-Loop-Graph.md
│   ├── Nested-Cycles.md
│   ├── Graph-Principles.md
│   ├── Eval-Engineering.md
│   ├── Diagram-Principles.md
│   └── RAI-Improvement.md
├── templates/
│   ├── Diamond-Research.md
│   ├── Graph-Engineering-Template.md
│   ├── Residue-Structure.md
│   ├── Handoff-Artifact.md
│   ├── RAI-Loop.md
│   └── Probe-Suite.md
├── personalities/
│   ├── README.md
│   └── … specialist packs
└── Projects/                          # Active work lives here (not shipped projects)
    ├── README.md                      # Path rules for agents
    ├── _index.md                      # Registry (starts empty)
    └── _template/                     # Copy → Projects/<slug>/
        ├── Overview.md
        └── Nested-HLG.md
```

### Projects path (important)

**Canonical location for active projects:**

```text
Projects/<project-slug>/
```

Copy `_template` when starting work. Register a line in `_index.md`. Keep residue inside that folder. Do **not** put project files in `core/`, `templates/`, or the repo root. See `Projects/README.md`.

Real project content is **never** part of this public pack by design (work-safe; offline/local git friendly).

## Purpose: Personal Research vs Work Projects

- **Private AI-Mind-Vault** = personal research, Grok-native surfaces, full methodology, thin project overviews, review process.
- **This pack** = portable Codex / GPT surface for work computers and shared environments: architecture + personalities + **empty project path**.

Architecture stays identical so the two surfaces remain aligned. Domain skills and personal catalogs stay in the Vault; the pack carries the durable core, neutral specialist packs, and a place for local active work.

## Recommended Codex / GPT Workflow

1. Start complex tasks in **plan mode** and write the topology (or Diamond) as files first.
2. If the work is a **project**, create `Projects/<slug>/` from `_template` and keep residue there.
3. Force **intentional residue**: every meaningful step writes durable artifacts.
4. Keep **Writer ≠ Checker**.
5. Use the Qualifying Test before multi-node graphs.
6. Put human gates only where risk is asymmetric.
7. **Before deploy**: run the Probe Suite via the RAI Loop and leave the LEDGER as residue.
8. Optionally load one personality pack for domain depth; it never overrides AGENTS.md.

## Regular Update Policy

- **Last synced from AI-Mind-Vault:** 2026-08-06 (Projects path rules)
- **Trigger a re-sync when:** AGENTS.md, Nested-Cycles, Graph Principles, RAI, Probe Suite, Handoff Spec, Eval Engineering, or the specialist personality set change in the private vault.
- **Owner action:** Ask GrokRarian (or any agent with vault access) to “sync codex-mind-pack” after those controlling documents are updated and approved.
- **This pack never auto-pulls.** All updates are intentional pushes.

## Changelog (pack)

### 2026-08-06 (evening)
- Added `Projects/` path scaffold: README (rules), `_index.md`, `_template/` (Overview + Nested-HLG).
- No real projects shipped — agents park active work under `Projects/<slug>/`.
- AGENTS.md + README document the binding path rule.

### 2026-08-06 (afternoon)
- Added `core/Nested-Cycles.md`, `core/Eval-Engineering.md`, `core/Diagram-Principles.md`.
- AGENTS.md points at Nested-Cycles, Eval, and Diagram Principles.

### 2026-08-06 (earlier)
- Added `personalities/` with 8 GPT/Codex-adapted specialist packs.
- Clarified pack purpose: separate personal research surface from work projects while keeping architecture aligned.
- Full sync of portable rules; Probe Suite expanded; Handoff template tightened.

Created 2026-08-03 / 2026-08-04. Maintained as the reliable GPT/Codex surface of the AI Mind.
