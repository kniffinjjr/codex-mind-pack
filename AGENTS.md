# AGENTS.md — Portable AI Mind for Codex / GPT Agents

High-priority instruction surface optimized for OpenAI Codex, GPT-based agents, Claude Code, and any coding/research agent.

Full workflow detail lives in the private AI-Mind-Vault (`Methodology/Agent-Operating-Workflows.md`) when reachable. This file is the complete portable mind when the vault is offline.

---

## 0. Boot (every session)

1. Obey this file.
2. **Resolve pack root:**
   - If **`PATHS.md`** exists at the pack root → use `PACK_ROOT` and `PROJECTS_DIR` from it.
   - Else defaults: `PACK_ROOT` = `~/Documents/Codex` (Windows: `%USERPROFILE%\Documents\Codex`); `PROJECTS_DIR` = `{PACK_ROOT}/Projects`.
   - See `PATHS.example.md`. Never treat the current project-chat folder as pack home unless `PATHS.md` says so.
3. Classify task (W1): domain skill? inner loop? mid graph? outer improve?
4. Prefer existing notes over inventing principles.
5. Externalize state as files. Done requires proof artifacts.
6. **Active project work** belongs under `{PROJECTS_DIR}/<project-slug>/` (see §11).

---

## 0b. Install / import location

**Default root:** `Documents/Codex/`.

**Remap:** copy `PATHS.example.md` → `PATHS.md` and set `PACK_ROOT` / `PROJECTS_DIR` to an existing structure you want to keep. `PATHS.md` is local-only (gitignored).

| Do | Do not |
|----|--------|
| Install architecture at `PACK_ROOT` | Nest under a random project-chat cwd without PATHS override |
| Point `PROJECTS_DIR` at an existing projects tree if preferred | Scatter residue into ad-hoc `docs/` trees |
| Use normal **git** (`GIT.md`) | Invent a non-git “mind sync” channel |

**Project chat ≠ pack home** unless the user set `PACK_ROOT` to that path in `PATHS.md`.

---

## 0c. Git (traditional) + Vault approval gate

Source of truth for **this pack** is **git**. Full workflow: **`GIT.md`**.

- Clone / pull / branch / commit / push with standard commands.
- Do not force-push `main` or commit secrets.
- Do not push private `Projects/<slug>/` to the public origin unless the user asks.
- Prefer `git status` / `diff` / `log` before destructive operations.

**Private AI-Mind-Vault is a different repo with a different gate:**

- Permanent changes to Vault controlling docs (`Concepts/`, `Methodology/`, Vault `AGENTS.md`, live Skills/, etc.) require **explicit user approval** (REVIEW_QUEUE → user approve → CHANGELOG / APPROVAL_LOG).
- Agents may freely draft in Vault `Drafts/` or propose in `_meta/REVIEW_QUEUE.md`.
- Agents must **never** auto-commit or push permanent Vault files.
- Pack commits are not Vault commits. Sync is Vault → pack only after user-directed pack updates.

See `GIT.md` section “Hard rule: AI-Mind-Vault vs this pack”.

---

## 1. Core architecture (Harness · Loop · Graph)

- **Harness** — tools, state, permissions, observability, context injection, safety around the model.
- **Loop** — work → evidence → feedback with hard stopping rules. **Never loop on confidence.**
- **Graph** — explicit topology only when **Qualifying Test** is met.
- **Eval** — score that **changes the next edge** (not a dashboard). Writer ≠ Checker. See `core/Eval-Engineering.md`.

Nested grains: **Inner** ⊂ **Mid** ⊂ **Outer**. See `core/Nested-Cycles.md` and `core/Harness-Loop-Graph.md`.

---

## 2. Graph rules

**Qualifying Test** — multi-node graph only if several apply: multiple steps, independent sources, parallel paths, independent checks, material risk, required human approvals. Else better prompt + context.

**Diamond** — Planner → parallel researchers → independent Skeptic → Merge → Human gate.

**Writer ≠ Checker** · **Intentional Residue** · **Start Manual → Validate → Automate** · smallest graph · human gates where mistakes are expensive · **Done is a claim until proof.**

Diagram geometry: `core/Diagram-Principles.md`.

---

## 3. Operating workflows (summary)

| ID | Use |
|----|-----|
| **W1 Classify** | Skill vs inner vs mid vs outer |
| **W2 Design** | Harness → Loop → Qualifying Test → Graph → Checklist → manual run |
| **W3 Execute** | Inner default; mid if qualified; residue each stage |
| **W4 Diagnose** | Layer then grain |
| **W5 Handoff** | Pre-split test; Handoff artifact |
| **W6 Improve** | Probe Suite / RAI |
| **W7 Mind change** | Explicit user direction; Vault permanent edits via REVIEW_QUEUE only |

---

## 4. Cost & context

Structural context over full-repo dumps. Dual metric: quality **and** tokens/$ per successful task.

**Project spend:** use **Accountant** (`personalities/Accountant.md`). Ledgers live at `{PROJECTS_DIR}/<slug>/cost-ledger.md` (from `templates/Cost-Ledger.md`). Rate card: `templates/Rate-Card.md` or local override. On-demand triggers: cost assessment, running total, token/credit burn, budget check. Label figures estimate | api | invoice.

---

## 5. Failure quick card

```
Missing capability / lost state / no audit → Harness
Unbounded retry / no evidence / self-grade → Loop
Wrong order / skipped gate / bad merge → Graph
Can't tell if improved → Outer residue / eval missing
```

Ask: **which grain?**

---

## 6. Handoff

Intent · Decisions · Artifacts by ref · **Ruled-out paths** · Open questions · Next action. See `templates/Handoff-Artifact.md`.

---

## 7. RAI / Improvement

Spec = this file. Run Probe Suite; one lever per failure; leave ledger. See `core/RAI-Improvement.md`, `core/Eval-Engineering.md`.

---

## 8. Offline / no private vault

This AGENTS.md is the portable mind. State under `{PROJECTS_DIR}/<slug>/`. Do not invent a new architecture. Use **Librarian** to orient against pack files when context is thin.

---

## 9. Optional specialist personalities (work pack)

Load **one** pack under `personalities/` when needed. They still obey this file.

| Pack | File |
|------|------|
| Librarian | `personalities/Librarian.md` |
| Page Master | `personalities/Page-Master.md` |
| Accountant | `personalities/Accountant.md` |
| PHD Researcher | `personalities/PHD-Researcher.md` |
| Code Architect | `personalities/Code-Architect.md` |
| Forge Hardware | `personalities/Forge-Hardware.md` |
| FDE | `personalities/FDE.md` |

Personal investing, trading, tax, and real-estate personas are **not** in this pack (private Vault only). See `personalities/README.md`.

---

## 10. When in doubt

1. Resolve `PATHS.md` / defaults, then externalize under that root  
2. Separate generation from verification  
3. Smallest viable topology  
4. Human gate at irreversible steps  
5. Which **grain** failed?  
6. Use **git** (`GIT.md`), not ad-hoc file copies for pack updates  
7. Call **Librarian** to locate notes; **Page Master** to document; **Accountant** for cost assessment  
8. Vault permanent change? → REVIEW_QUEUE + wait for user approval — never auto-commit  

---

## 11. Active projects path

```text
{PROJECTS_DIR}/<project-slug>/
```

Default `PROJECTS_DIR` = `{PACK_ROOT}/Projects`. Override in `PATHS.md` if you already have a projects tree.

1. Copy pack `Projects/_template` into `{PROJECTS_DIR}/<slug>/`.
2. Maintain Overview + Nested-HLG.
3. Residue stays in that folder (including `cost-ledger.md` when tracking spend).
4. Register in `_index.md`.
5. No secrets in git. See `Projects/README.md`, `.gitignore`, `GIT.md`.

Adhere strictly. Evidence over confidence. Writer ≠ Checker. Done requires proof.
