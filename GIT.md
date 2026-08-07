# Git workflow — codex-mind-pack

Traditional git is the source of truth for **this pack**. Agents and humans use normal git operations. Do not invent a parallel “mind sync” protocol.

---

## Hard rule: AI-Mind-Vault vs this pack

| Surface | What it is | Who may commit permanent changes |
|---------|------------|----------------------------------|
| **Private AI-Mind-Vault** (`kniffinjjr/AI-Mind-Vault`) | Personal research, controlling methodology, Grok-native surfaces, project overviews, Review Queue | **User only** after explicit approval (REVIEW_QUEUE → approve → CHANGELOG / APPROVAL_LOG) |
| **codex-mind-pack** (this repo) | Portable Codex / GPT work surface | User or agent under user direction for **pack architecture only** |

**Agents must never:**

- Push or merge into `AI-Mind-Vault` without the user saying so after a REVIEW_QUEUE proposal.
- Treat a commit in this pack as a change to Vault controlling docs (`Concepts/`, `Methodology/`, Vault `AGENTS.md`, `Skills/`, `_meta/` live notes, etc.).
- “Sync back” pack experiments into the Vault automatically.

**Sync direction (by design):**

1. Vault is source of truth for architecture principles.
2. After user approval of Vault changes, an agent may be asked to **update this pack** (intentional push to `codex-mind-pack`).
3. Local work residue stays under `Projects/<slug>/` (or private remote) and does **not** flow into the public Vault.

If a change belongs in the Vault, the agent drafts a proposal in the Vault’s `_meta/REVIEW_QUEUE.md` (or Drafts/) and **stops**. The user approves or rejects. Only then is the live Vault file updated.

Full Vault gate: private repo `Process/Approval-Workflow.md` and `_meta/Vault-Conventions.md`.

---

## Remote

```text
https://github.com/kniffinjjr/codex-mind-pack.git
```

Default branch: **`main`**

---

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

---

## First-time install (existing folder you want to keep)

```bash
cd /path/to/your-existing-root
git init   # only if not already a git repo
git remote add origin https://github.com/kniffinjjr/codex-mind-pack.git
git fetch origin
git checkout -b main origin/main   # or merge carefully if you have local files
cp PATHS.example.md PATHS.md
# Edit PATHS.md so PACK_ROOT / PROJECTS_DIR match this machine
```

Or clone into a temp dir and copy only architecture files (`AGENTS.md`, `core/`, `templates/`, `personalities/`, `Projects/_template`, `Projects/README.md`, `Projects/_index.md`) into your root — then set `PATHS.md` accordingly.

---

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

---

## What to commit where

| Path | Commit to public `origin`? | Notes |
|------|----------------------------|--------|
| `AGENTS.md`, `core/`, `templates/`, `personalities/` | Yes (if maintaining a fork or upstream) | Architecture |
| `GIT.md`, `PATHS.example.md`, `.gitignore`, `README.md` | Yes | Setup docs |
| `Projects/_template/`, `Projects/README.md`, empty `_index` | Yes | Scaffold only |
| `Projects/<your-slug>/` | **Usually no** (local or private remote) | Work residue; may contain internal data |
| `PATHS.md` | **Never** | Machine-specific |
| Secrets, `.env`, credentials | **Never** | Use `.gitignore` |
| Anything under private **AI-Mind-Vault** | **Only after user approval via REVIEW_QUEUE** | Separate repo; separate gate |

---

## Daily / project residue (local git)

Keep **one local git repo** at `PACK_ROOT` and **do not push** `Projects/*` to the public GitHub remote unless the user asks:

```bash
git status
git add Projects/my-slug/
git commit -m "feat(my-slug): progress notes"
# optional private remote:
# git remote add private git@github.com:you/codex-mind-private.git
# git push private main
```

Or use a **separate git repo** only for `PROJECTS_DIR` if that directory lives outside the pack.

---

## Branching (optional)

```bash
git checkout -b work/my-slug
# ... edits under Projects/my-slug or pack docs ...
git add -p
git commit -m "describe change"
git checkout main
git merge work/my-slug   # when ready
```

For contributions back to the **public pack** (architecture only), open a PR against `kniffinjjr/codex-mind-pack` from a fork — do not include private project folders or Vault paths.

---

## .gitignore (shipped)

The repo ignores `PATHS.md`, common secret patterns, and optionally local project bulk. See `.gitignore`. Adjust locally if you *do* want to track specific project folders on a private remote.

---

## Agent rules (git + Vault gate)

1. Prefer `git status`, `git diff`, `git log` before destructive commands.
2. Do not `git push` to public `origin` unless the user asks and the change is architecture-safe for this pack.
3. Do not force-push `main`.
4. Do not commit secrets; stop and warn if they appear in `git status`.
5. Resolve `PATHS.md` before writing files so commits land under the user’s chosen root.
6. **Vault gate:** if a change belongs in private AI-Mind-Vault controlling docs, draft a REVIEW_QUEUE proposal (or Drafts/) and **wait for explicit user approval**. Never auto-apply permanent Vault edits.
7. Pack commits ≠ Vault commits. Keep the two remotes and approval processes separate.
