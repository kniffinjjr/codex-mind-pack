# codex-mind-pack

**Portable AI Mind pack optimized for OpenAI Codex and GPT-based agents** (also usable with Claude Code and other coding agents).

This repository is the **public, work-safe surface** of the private AI-Mind-Vault. It keeps the same Harness · Loop · Graph architecture, Nested Cycles, RAI discipline, and Probe Suite so personal research and work projects stay aligned, while cleanly separating Grok-native personal surfaces from Codex/GPT work surfaces.

---

## Canonical install location (binding)

**On the user’s machine, this pack lives at the root of the Codex folder in Documents — not inside any project chat workspace.**

```text
~/Documents/Codex/          # Windows: %USERPROFILE%\Documents\Codex\
├── AGENTS.md
├── README.md
├── LICENSE
├── core/
├── templates/
├── personalities/
└── Projects/               # active work only — see Projects/README.md
    ├── _index.md
    ├── _template/
    └── <project-slug>/     # created when work starts
```

### Rules for Codex (and any agent doing install/import)

1. **Target root** = `Documents/Codex/` (create if missing).
2. **Contents of this repo** go **at that root** (or replace an existing clone there). Do **not** nest a second `codex-mind-pack/` folder under a project such as `AI DEV/`, `ai-dev-workspace/`, or the current chat’s working directory.
3. **Project chat ≠ pack home.** If the user is in a project chat (e.g. “AI DEV”), still install/update the mind pack under `Documents/Codex/`. Project residue belongs under `Documents/Codex/Projects/<slug>/`, not under the chat’s ad-hoc tree.
4. **Do not** invent parallel trees like `docs/`, `codex-mind-pack/` nested inside a project, or duplicate `AGENTS.md` at the project root unless the user explicitly asks for a one-off copy.

### Correct vs incorrect layout

**Correct**

```text
Documents/Codex/
├── AGENTS.md
├── core/
├── templates/
├── personalities/
└── Projects/
    └── configurator-dev/
```

**Incorrect** (what must not happen)

```text
AI DEV/                          # project chat workspace
├── AGENTS.md
├── codex-mind-pack/             # nested pack — wrong
├── Projects/
└── docs/
```

---

## Quick Start

```bash
# Preferred: clone directly into Documents/Codex
mkdir -p ~/Documents/Codex
git clone https://github.com/kniffinjjr/codex-mind-pack.git ~/Documents/Codex
# If the folder already exists and is the pack root:
cd ~/Documents/Codex && git pull origin main
```

Optional global pointer (Codex product config):

```bash
mkdir -p ~/.codex
cp ~/Documents/Codex/AGENTS.md ~/.codex/AGENTS.md
```

**Active project work:** only under `~/Documents/Codex/Projects/<slug>/`. This pack does **not** ship real projects.

---

## What This Pack Provides

- **AGENTS.md** — high-priority durable instructions agents are trained to follow.
- Core Harness · Loop · Graph + **Nested Cycles** (Inner ⊂ Mid ⊂ Outer).
- **Eval Engineering**, Graph rules, **Diagram Principles**, **RAI** + **Probe Suite**.
- Templates for planning, residue, and handoffs.
- **Work-pack personalities only:** PHD Researcher, Code Architect, Forge Hardware, FDE.
- **Projects/** — path + templates only; agents park active work here under `Documents/Codex/`.

## Structure (repo = Documents/Codex root)

```text
Documents/Codex/   # same layout as this repository root
├── AGENTS.md
├── README.md
├── LICENSE
├── core/
├── templates/
├── personalities/
└── Projects/
    ├── README.md
    ├── _index.md
    └── _template/
```

## Purpose: Personal Research vs Work Projects

- **Private AI-Mind-Vault** = personal research, Grok-native surfaces, full methodology.
- **This pack at `Documents/Codex/`** = portable Codex/GPT surface for work machines: architecture + work personalities + empty project path.

## Recommended Codex / GPT Workflow

1. Confirm mind pack root is `Documents/Codex/` before writing files.
2. Plan mode + topology files first for complex tasks.
3. Project work → `Projects/<slug>/` from `_template`; residue stays there.
4. Writer ≠ Checker; Qualifying Test before multi-node graphs; human gates on irreversible steps.
5. Before deploy: Probe Suite + RAI Loop; leave ledger as residue.
6. Optional: one personality pack; never overrides `AGENTS.md`.

## Regular Update Policy

- **Last synced:** 2026-08-06 (install root = Documents/Codex; work personalities only)
- Re-sync when controlling architecture or the work personality set changes in the private vault.
- This pack never auto-pulls.

## Changelog (pack)

### 2026-08-06 (install root)
- Documented **canonical root**: `~/Documents/Codex/` (Windows: `%USERPROFILE%\Documents\Codex\`).
- Explicit rule: do not nest the pack under a project chat workspace.
- Work personalities only: PHD, Code Architect, Forge, FDE.

### 2026-08-06 (evening)
- Added `Projects/` path scaffold; no real projects shipped.

### 2026-08-06 (afternoon / earlier)
- Nested-Cycles, Eval, Diagram Principles; personality set refined.

Created 2026-08-03 / 2026-08-04. Maintained as the reliable GPT/Codex surface of the AI Mind.
