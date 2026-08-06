# Projects/ — where active work lives

This pack does **not** ship real project content. `Projects/` is the **canonical path** for any active project Codex (or you) creates while using this mind pack.

## Path rule (binding for agents)

When starting or continuing project work under this pack:

```text
codex-mind-pack/Projects/<project-slug>/
```

Examples:

```text
Projects/acme-bom-export/
Projects/internal-eco-scorecard/
Projects/pdm-task-host-spike/
```

**Do not** dump project residue into `core/`, `templates/`, `personalities/`, or the repo root.

## What belongs in a project folder

| Keep here | Do not put here |
|-----------|-----------------|
| `Overview.md` — thin status + goals | Secrets, tokens, passwords |
| `Nested-HLG.md` — grain map for this job | Customer PII or controlled data beyond policy |
| Working notes, plans, residue, handoffs | Full copies of `core/` architecture (link instead) |
| Local drafts, checklists, probe ledgers | Permanent methodology changes (those go to the private vault when available) |

## How to start a project

1. Copy the template:
   ```bash
   cp -R Projects/_template Projects/my-project-slug
   ```
2. Edit `Overview.md` and `Nested-HLG.md`.
3. Put all mid-grain residue under that folder.
4. Register a one-line entry in `Projects/_index.md`.

## Work vs personal surfaces

- **This pack (often on a work machine):** active project folders under `Projects/` — local git is fine; no requirement to push to GitHub.
- **Private AI-Mind-Vault (personal):** thin project overviews and controlling methodology when GitHub is available.
- Architecture stays aligned via `AGENTS.md` + `core/`; project *data* stays out of the public pack by design.

## Agent checklist

- [ ] Active project path is `Projects/<slug>/`
- [ ] Overview + Nested-HLG exist before multi-step work
- [ ] Residue stays inside that folder
- [ ] No secrets committed
- [ ] `_index.md` updated with a one-line pointer
