# PATHS — local path map (example)

Copy this file to **`PATHS.md`** in the pack root and edit it if you are **not** using the defaults.

`PATHS.md` is gitignored (local only). Agents must read `PATHS.md` when present; otherwise use the defaults below.

## Defaults (when PATHS.md is absent)

| Key | Default |
|-----|---------|
| `PACK_ROOT` | `~/Documents/Codex` (Windows: `%USERPROFILE%\Documents\Codex`) |
| `PROJECTS_DIR` | `{PACK_ROOT}/Projects` |
| `GLOBAL_AGENTS` | `~/.codex/AGENTS.md` (optional copy) |

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
