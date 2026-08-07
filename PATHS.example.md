# PATHS — local path map (example)

Copy this file to **`PATHS.md`** in the pack root and edit it if you are **not** using the defaults.

`PATHS.md` is gitignored (local only). Agents must read `PATHS.md` when present; otherwise use the defaults below.

**Owner of path orientation:** the **Librarian** (`personalities/Librarian.md`). Any agent that is unsure where the pack or projects live must resolve via this map or hand off to Librarian — never invent a third root.

## Defaults (when PATHS.md is absent)

| Key | Default |
|-----|---------|
| `PACK_ROOT` | `~/Documents/Codex` (Windows: `%USERPROFILE%\Documents\Codex`) |
| `PROJECTS_DIR` | `{PACK_ROOT}/Projects` |
| `GLOBAL_AGENTS` | `~/.codex/AGENTS.md` (optional copy) |

## Location rules

| Artifact | Where it lives |
|----------|----------------|
| Architecture (`AGENTS.md`, `core/`, `templates/`, `personalities/`) | `{PACK_ROOT}/` |
| Active project residue (including `cost-ledger.md`) | `{PROJECTS_DIR}/<slug>/` |
| This map | `{PACK_ROOT}/PATHS.md` (local only) |
| Example map (committed) | `{PACK_ROOT}/PATHS.example.md` |

**Install root is not the current project-chat cwd** unless `PATHS.md` explicitly sets `PACK_ROOT` there.

## Example: keep an existing layout

```markdown
# PATHS.md — local overrides (do not commit secrets)

PACK_ROOT: D:/Work/AI-Mind-Codex
PROJECTS_DIR: D:/Work/AI-Mind-Codex/Projects
GLOBAL_AGENTS: C:/Users/you/.codex/AGENTS.md

# Optional: if active work already lives elsewhere, point at it instead of migrating
# PROJECTS_DIR: D:/Work/existing-projects-tree
```

## Example: macOS / Linux custom

```markdown
PACK_ROOT: /Users/you/src/codex-mind
PROJECTS_DIR: /Users/you/src/codex-mind/Projects
```

## Rules for agents

1. If `PATHS.md` exists at pack root → use those absolute or home-relative paths.
2. If not → use defaults (`Documents/Codex`).
3. Never invent a third root under a project-chat cwd.
4. Never commit `PATHS.md` (it may contain machine-specific paths).
5. `PROJECTS_DIR` may point outside `PACK_ROOT` when the user already has a structure they want to keep; still keep architecture files under `PACK_ROOT`.
6. **Librarian controls orientation** — on cold start or path confusion, activate Librarian; do not guess roots.
7. **Accountant**, Page Master, and other specialists read the same map; they do not redefine it.
8. Changes to committed path *policy* (this example, AGENTS §0, Librarian rules) require user direction and a normal pack git commit — not silent agent rewrites.
