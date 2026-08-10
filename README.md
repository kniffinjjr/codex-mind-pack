# codex-mind-pack

**Portable AI Mind pack** for OpenAI Codex, GPT agents, Claude Code, and similar tools.

Public, work-safe surface of the private AI-Mind-Vault: same Harness · Loop · Graph architecture, without personal Grok-only surfaces.

---

## Default install location

```text
~/Documents/Codex/          # Windows: %USERPROFILE%\Documents\Codex\
├── AGENTS.md
├── PATHS.example.md        # copy → PATHS.md to remap
├── GIT.md                  # traditional git workflow + Vault approval gate
├── Skills/                 # Agent ↔ Skill map (work-safe)
├── core/
├── templates/
├── personalities/
└── Projects/
```

**Do not** nest this pack under a project-chat folder unless you deliberately set that path in `PATHS.md`.

---

## Remap if you already have a structure

1. Copy `PATHS.example.md` → **`PATHS.md`** (gitignored, local only).
2. Set `PACK_ROOT` and `PROJECTS_DIR` as needed.
3. Agents read `PATHS.md` when present; otherwise use Documents/Codex defaults.

Details: **`PATHS.example.md`**.

---

## Git (traditional) + Vault gate

This pack is a normal git repo. See **`GIT.md`**.

```bash
mkdir -p ~/Documents/Codex
git clone https://github.com/kniffinjjr/codex-mind-pack.git ~/Documents/Codex
cd ~/Documents/Codex
cp PATHS.example.md PATHS.md   # optional remap
git pull origin main           # updates
```

| Repo | Permanent changes require |
|------|---------------------------|
| **codex-mind-pack** (this) | User direction for architecture; normal git |
| **AI-Mind-Vault** (private) | Explicit user **approval** via REVIEW_QUEUE |

Agents must not auto-commit to the Vault. See **`GIT.md`**.

---

## What this pack provides

| Area | Contents |
|------|----------|
| Boot | `AGENTS.md` |
| Architecture | `core/` (HLG, Nested Cycles, Graph, Eval, Diagram, RAI, Lessons) |
| **Skills map** | `Skills/Agent-Skill-Map.md` — persona → skill routing (work-safe) |
| Templates | Diamond, Handoff, Probe Suite, Residue, Cost Ledger, Lessons, … |
| Personalities | Librarian, Page Master, Lessons Learned, Accountant, PHD Researcher, Code Architect, Forge Hardware, FDE |
| Projects path | Scaffold only |
| Paths / Git | `PATHS.example.md`, `GIT.md`, `.gitignore` |

---

## Agent install rules (short)

1. Resolve `PATHS.md` → else `Documents/Codex`.
2. Write architecture under `PACK_ROOT`.
3. Write active work under `PROJECTS_DIR/<slug>/`.
4. Project chat ≠ pack home unless PATHS says so.
5. Use git per `GIT.md`.
6. **Vault permanent edits → REVIEW_QUEUE + user approval only.**
7. Skill vs personality → `Skills/Agent-Skill-Map.md`.

---

## Changelog

### 2026-08-10
- `Skills/Agent-Skill-Map.md` + `Skills/README.md` — work-safe persona→skill routing aligned with Vault map.
- AGENTS.md / README point at the skills map.

### 2026-08-07
- `GIT.md` expanded: hard separation from private AI-Mind-Vault; permanent Vault changes require user approval.

### 2026-08-06
- PATHS + git install docs; projects scaffold; work personalities.

Created 2026-08-03 / 2026-08-04.
