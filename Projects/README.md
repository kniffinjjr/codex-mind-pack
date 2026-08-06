# Projects/ — where active work lives

This pack does **not** ship real project content. Active projects go under **`PROJECTS_DIR`**.

## Resolve path first

1. If **`PATHS.md`** exists at pack root → use its `PROJECTS_DIR`.
2. Else default: `{PACK_ROOT}/Projects` with `PACK_ROOT` = `~/Documents/Codex` (Windows: `%USERPROFILE%\Documents\Codex`).

You may point `PROJECTS_DIR` at an **existing** projects tree you want to keep; architecture files still live under `PACK_ROOT`.

See `PATHS.example.md` and `GIT.md`.

## Path rule

```text
{PROJECTS_DIR}/<project-slug>/
```

Examples (default layout):

```text
Documents/Codex/Projects/configurator-dev/
Documents/Codex/Projects/pdm-task-host-spike/
```

**Do not** put project residue in `core/`, `templates/`, `personalities/`, or a project-chat ad-hoc `docs/` tree.

## Start a project

```bash
# defaults; substitute PROJECTS_DIR from PATHS.md if set
cp -R "$PACK_ROOT/Projects/_template" "$PROJECTS_DIR/my-project-slug"
```

Edit `Overview.md` and `Nested-HLG.md`. Register a line in `_index.md`. Use **git** for history (`GIT.md`).

## Agent checklist

- [ ] Read `PATHS.md` if present
- [ ] Active path = `{PROJECTS_DIR}/<slug>/`
- [ ] Overview + Nested-HLG before multi-step work
- [ ] Residue stays in that folder
- [ ] No secrets committed
