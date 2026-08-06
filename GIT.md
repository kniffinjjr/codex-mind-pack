# Git workflow — codex-mind-pack

Traditional git is the source of truth for this pack. Agents and humans should use normal git operations; do not invent a parallel “mind sync” protocol.

## Remote

```text
https://github.com/kniffinjjr/codex-mind-pack.git
```

Default branch: **`main`**

## First-time install (default root)

```bash
mkdir -p ~/Documents/Codex
git clone https://github.com/kniffinjjr/codex-mind-pack.git ~/Documents/Codex
cd ~/Documents/Codex
cp PATHS.example.md PATHS.md   # optional; edit if remapping
```

Windows (PowerShell):

```powershell
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\Documents\Codex"
git clone https://github.com/kniffinjjr/codex-mind-pack.git "$env:USERPROFILE\Documents\Codex"
cd "$env:USERPROFILE\Documents\Codex"
Copy-Item PATHS.example.md PATHS.md
```

## First-time install (existing folder you want to keep)

If you already have a directory structure:

```bash
cd /path/to/your-existing-root
git init   # only if not already a git repo
git remote add origin https://github.com/kniffinjjr/codex-mind-pack.git
git fetch origin
git checkout -b main origin/main   # or merge carefully if you have local files
# Write PATHS.md so PACK_ROOT / PROJECTS_DIR match this machine
cp PATHS.example.md PATHS.md
```

Or clone into a temp dir and copy only `AGENTS.md`, `core/`, `templates/`, `personalities/`, `Projects/_template`, `Projects/README.md`, `Projects/_index.md` into your root — then set `PATHS.md` accordingly.

## Update from upstream

```bash
cd "$PACK_ROOT"    # default: ~/Documents/Codex
git checkout main
git pull origin main
```

If you have local commits on top of the pack:

```bash
git pull --rebase origin main
# or: git fetch origin && git merge origin/main
```

## What to commit where

| Path | Commit to public `origin`? | Notes |
|------|----------------------------|--------|
| `AGENTS.md`, `core/`, `templates/`, `personalities/` | Yes (if you maintain a fork) | Architecture |
| `Projects/_template/`, `Projects/README.md`, empty `_index` | Yes | Scaffold only |
| `Projects/<your-slug>/` | **Usually no** (local or private remote) | Work residue; may contain internal data |
| `PATHS.md` | **Never** | Machine-specific |
| Secrets, `.env`, credentials | **Never** | Use `.gitignore` |

## Daily / project residue (local git)

Many users keep **one local git repo** at `PACK_ROOT` and **do not push** `Projects/*` to the public GitHub remote:

```bash
git status
git add Projects/my-slug/
git commit -m "feat(my-slug): progress notes"
# optional private remote:
# git remote add private git@github.com:you/codex-mind-private.git
# git push private main
```

Or use a **separate git repo** only for `PROJECTS_DIR` if that directory lives outside the pack.

## Branching (optional)

```bash
git checkout -b work/my-slug
# ... edits under Projects/my-slug or pack docs ...
git add -p
git commit -m "describe change"
git checkout main
git merge work/my-slug   # when ready
```

For contributions back to the public pack (architecture only), open a PR against `kniffinjjr/codex-mind-pack` from a fork — do not include private project folders.

## .gitignore (shipped)

The repo ignores `PATHS.md`, common secret patterns, and optionally local project bulk. See `.gitignore`. Adjust locally if you *do* want to track specific project folders in a private remote.

## Agent rules (git)

1. Prefer `git status`, `git diff`, `git log` before destructive commands.
2. Do not `git push` to `origin` unless the user asks and the change is architecture-safe.
3. Do not force-push `main`.
4. Do not commit secrets; stop and warn if they appear in `git status`.
5. Resolve `PATHS.md` before writing files so commits land under the user’s chosen root.
