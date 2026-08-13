# Hypervault on Work Mind (Codex implementation)

**Purpose:** Use [Hypervault](https://studio.pardesco.com/hypervault) (Obsidian 3D city / agent command center) **only** against work project residue — never personal My-Mind or the portable pack `core/`.

This pack does **not** reimplement the Three.js city. It provides the **work-safe wiring**: vault root, frontmatter, project detection, agent launch paths, and IP rules.

Upstream product: Hypervault Free (Obsidian plugin, AGPL) or Pro (standalone). Schema fields below match Hypervault’s public frontmatter schema.

---

## Hard rules (IP firewall)

| Do | Do not |
|----|--------|
| Point Obsidian / Hypervault at a **Work-only** vault root | Open personal My-Mind or home notes in the same vault |
| Keep buildings = **work projects** under `PROJECTS_DIR` | Mix company IP with personal residue |
| Launch agents only into `projectDir` under work paths | Launch agents into pack `core/`, `templates/`, or home |
| Store instance extracts under `Projects/<slug>/knowledge/extract/` | Copy work extracts into this pack’s git tree as “the database” |

`PACK_ROOT` (architecture) and the **Hypervault vault root** may differ. Prefer:

```text
PACK_ROOT          → Documents/Codex  (AGENTS.md, core/, templates/)
HYPERVAULT_VAULT   → same as PROJECTS_DIR, or a sibling Work-Obsidian vault
                     that only contains work project notes + links to code dirs
```

Resolve paths via `PATHS.md` (see `PATHS.example.md`). Optional key you may add locally:

```markdown
HYPERVAULT_VAULT: D:/Work/Work-Mind-Vault
PROJECTS_DIR: D:/Work/Work-Mind-Vault/Projects
```

---

## Install (work machine)

1. Install **Obsidian** (company-approved if required).
2. Create or open a vault whose root is **only** work content (recommend: `{PROJECTS_DIR}` parent or dedicated Work-Mind vault).
3. Install **Hypervault** plugin (Community plugins or manual from upstream repo) **or** Hypervault Pro if licensed for work.
4. Confirm plugin settings: project detection tag = `project` (default).
5. Do **not** enable agent launch until `projectDir` frontmatter points at real work folders.

---

## What becomes a building

Hypervault treats a note as a project if:

- `type: project`, **or**
- `tags` includes `project`

**Codex convention:** one building per active work project = that project’s `Overview.md` (or a dedicated `Project.md`) under:

```text
{PROJECTS_DIR}/<slug>/Overview.md
```

Optional: a flat `Projects/` index note is fine; prefer per-folder Overview so `projectDir` is unambiguous.

---

## Required frontmatter (copy onto each work project Overview)

Full template: `templates/Project-Overview-Hypervault.md`.

Minimum:

```yaml
---
type: project
tags: [project, work]
title: <Human project name>
status: active          # active | blocked | paused | complete
priority: medium        # critical | high | medium | low
category: engineering   # district — e.g. engineering | analytics | ops | product
stage: active           # backlog | active | paused | complete
projectDir: "D:/Work/repos/<slug>"   # REQUIRED for Launch agent / Open folder
stack: [python, solidworks]          # optional tooltip
health: 80                           # optional 0–100
---
```

### Visual map (Hypervault)

| Field | City effect |
|-------|-------------|
| `status` | Building **color** (active=green, blocked=red, paused=blue, complete=purple) |
| `priority` | Building **height** |
| `category` | **District** |
| `stage` | Pipeline axis |
| `projectDir` | Agent / folder launch target |
| `questions` / `answered` | Open vs resolved quests (if plugin version supports) |
| `blocked_by` / `depends_on` | Dependency edges |

---

## Recommended Work vault layout

```text
{HYPERVAULT_VAULT}/                 # Obsidian vault root (work only)
  _meta/
    PATHS-note.md                   # optional human reminder of PATHS.md keys
  Projects/
    <slug>/
      Overview.md                   # type: project + Hypervault frontmatter
      Lessons-Learned.md            # optional
      knowledge/
        sources/
        extract/
          README.md
          YYYY-MM-DD-<slug>.md      # Run Knowledge Extract
      notes/                        # optional working notes (not all are buildings)
  Archive/                          # completed projects moved here; status: complete
```

Code repos may live **outside** the vault; set `projectDir` to the real checkout path so “Launch agent” opens the right folder.

---

## Agent launch (work-safe)

1. Only launch into directories listed in `projectDir` under company control.
2. Prefer company-approved CLIs (Codex, internal agents). Disable or avoid consumer keys if policy forbids.
3. After a meaningful multi-source run, deposit **`templates/Run-Knowledge-Extract.md`** under that project’s `knowledge/extract/` — the city does not replace residue.
4. Librarian / PATHS still own orientation; Hypervault is a **viewer + launcher**, not the source of truth for architecture.

---

## Mapping Codex pack personalities

| Need | Use |
|------|-----|
| Where is the vault / project path? | Librarian + `PATHS.md` |
| File an extract / guide | Page Master + Run Knowledge Extract |
| Architecture review of agent flows | HLG (`core/Harness-Loop-Graph.md`) |
| Cost of agent runs | Accountant + project `cost-ledger.md` |

Hypervault does not replace these roles.

---

## Checklist before first work use

- [ ] Vault root contains **only** work projects / work notes
- [ ] Each active project has `Overview.md` with `type: project` and `projectDir`
- [ ] `projectDir` paths are correct on this machine
- [ ] Personal My-Mind is a **separate** Obsidian vault (or not installed here)
- [ ] Pack `core/` is not the Hypervault root
- [ ] Run Knowledge Extract path known for at least one pilot project

---

## Related

- `PATHS.example.md` — remap pack and projects
- `templates/Project-Overview-Hypervault.md` — copy-paste frontmatter
- `templates/Run-Knowledge-Extract.md` — persistent nodes/edges after runs
- `templates/Project-Knowledge-Extract-README.md` — extract folder README
- `core/Harness-Loop-Graph.md` — hard stops; city UI is not a loop
