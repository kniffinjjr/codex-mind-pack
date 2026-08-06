# codex-mind-pack

**Portable AI Mind pack** for OpenAI Codex, GPT agents, Claude Code, and similar tools.

Public, work-safe surface of the private AI-Mind-Vault: same Harness · Loop · Graph architecture, without personal Grok-only surfaces.

---

## Default install location

```text
~/Documents/Codex/          # Windows: %USERPROFILE%\Documents\Codex\
├── AGENTS.md
├── PATHS.example.md        # copy → PATHS.md to remap
├── GIT.md                  # traditional git workflow
├── core/
├── templates/
├── personalities/
└── Projects/
```

**Do not** nest this pack under a project-chat folder (e.g. `AI DEV/codex-mind-pack/`) unless you deliberately set that path in `PATHS.md`.

---

## Remap if you already have a structure

1. Copy `PATHS.example.md` → **`PATHS.md`** (gitignored, local only).
2. Set:
   - `PACK_ROOT` — where architecture files live
   - `PROJECTS_DIR` — where active projects live (may be outside `PACK_ROOT`)
3. Agents read `PATHS.md` when present; otherwise use Documents/Codex defaults.

Example: keep projects on `D:/Work/projects` while pack architecture stays on `D:/Work/codex-mind`.

Details: **`PATHS.example.md`**.

---

## Git (traditional)

This pack is a normal git repo. Use clone, pull, branch, commit, push — see **`GIT.md`**.

```bash
# Default install
mkdir -p ~/Documents/Codex
git clone https://github.com/kniffinjjr/codex-mind-pack.git ~/Documents/Codex
cd ~/Documents/Codex
cp PATHS.example.md PATHS.md   # optional remap

# Update
git pull origin main
```

- Do not commit secrets or `PATHS.md`.
- Prefer not to push private `Projects/<slug>/` to the public origin.
- Optional private remote for work residue — described in `GIT.md`.

---

## What this pack provides

| Area | Contents |
|------|----------|
| Boot | `AGENTS.md` |
| Architecture | `core/` (HLG, Nested Cycles, Graph, Eval, Diagram, RAI) |
| Templates | Diamond, Handoff, Probe Suite, Residue, … |
| Personalities (work) | PHD Researcher, Code Architect, Forge Hardware, FDE |
| Projects path | Scaffold only — no shipped real projects |
| Paths / Git | `PATHS.example.md`, `GIT.md`, `.gitignore` |

---

## Agent install rules (short)

1. Resolve `PATHS.md` → else `Documents/Codex`.
2. Write architecture under `PACK_ROOT`.
3. Write active work under `PROJECTS_DIR/<slug>/`.
4. Project chat ≠ pack home unless PATHS says so.
5. Use git per `GIT.md`.

---

## Changelog

### 2026-08-06 (paths + git)
- `PATHS.example.md` — remappable `PACK_ROOT` / `PROJECTS_DIR`.
- `GIT.md` — traditional git clone/pull/branch/commit policy.
- `.gitignore` — `PATHS.md`, secrets, local noise.
- Default root remains `Documents/Codex/`; existing layouts can opt out via PATHS.

### 2026-08-06 (earlier)
- Projects scaffold; work personalities only; install-root docs.

Created 2026-08-03 / 2026-08-04.
