# Projects/ — where active work lives

This pack does **not** ship real project content. `Projects/` is the **canonical path** for any active project Codex (or you) creates while using this mind pack.

## Pack root (read first)

The mind pack root on the user’s machine is:

```text
~/Documents/Codex/     # Windows: %USERPROFILE%\Documents\Codex\
```

**Not** the current project-chat folder (e.g. not `AI DEV/`). Agents must not nest the pack or `Projects/` under a chat workspace.

## Path rule (binding for agents)

```text
Documents/Codex/Projects/<project-slug>/
```

Examples:

```text
Documents/Codex/Projects/acme-bom-export/
Documents/Codex/Projects/configurator-dev/
Documents/Codex/Projects/pdm-task-host-spike/
```

**Do not** dump project residue into `core/`, `templates/`, `personalities/`, the pack root, or a project-chat tree such as `AI DEV/docs/`.

## What belongs in a project folder

| Keep here | Do not put here |
|-----------|-----------------|
| `Overview.md` — thin status + goals | Secrets, tokens, passwords |
| `Nested-HLG.md` — grain map for this job | Customer PII beyond policy |
| Working notes, plans, residue, handoffs | Full copies of `core/` (link instead) |
| Local drafts, checklists, probe ledgers | The mind pack itself nested inside the project |

## How to start a project

1. Ensure pack root is `Documents/Codex/`.
2. Copy the template:
   ```bash
   cp -R ~/Documents/Codex/Projects/_template ~/Documents/Codex/Projects/my-project-slug
   ```
3. Edit `Overview.md` and `Nested-HLG.md`.
4. Put all mid-grain residue under that folder.
5. Register a one-line entry in `Projects/_index.md`.

## Agent checklist

- [ ] Pack root is `Documents/Codex/` (not the project chat cwd)
- [ ] Active project path is `Documents/Codex/Projects/<slug>/`
- [ ] Overview + Nested-HLG exist before multi-step work
- [ ] Residue stays inside that folder
- [ ] No secrets committed
- [ ] `_index.md` updated with a one-line pointer
