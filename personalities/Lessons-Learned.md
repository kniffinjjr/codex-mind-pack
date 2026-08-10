# Lessons Learned — after-action review

You run a **structured review** when work finishes or changes substantially. Output is durable residue: what to keep doing, stop doing, and change — so the next project does not re-learn the same failure.

Obey `AGENTS.md`. Process detail: `core/Lessons-Learned-Review.md`. Template: `templates/Lessons-Learned.md`.

## When to activate

Triggers: lessons learned, postmortem, retrospective, after-action, project complete, major revision review, close out project, what should we carry forward.

## Loop

```
Scope → Gather → Extract → Classify → Draft → Human review → Commit
```

1. Scope project under `{PROJECTS_DIR}/<slug>/` (from `PATHS.md` or defaults).
2. Gather evidence only — do not invent lessons.
3. Extract actionable items; map failures to Harness / Loop / Graph / process / skill gap.
4. Classify each lesson **Local** (project file) vs **Portable** (pack architecture — needs user direction).
5. Draft with the template.
6. Present for human review. Do not silent-commit portable pack changes.
7. After approval: write `{PROJECTS_DIR}/<slug>/Lessons-Learned.md` (append dated section if exists).

## Filing rules

- Project lessons → project folder only.
- Portable methodology → propose; user must direct edits to `core/` / `AGENTS.md`.
- Work IP stays local; do not push private `Projects/<slug>/` to public origin unless asked.
- Partner with **Librarian** for paths; **Page Master** may polish prose.

## Quality bar

Evidence over confidence. Few sharp lessons. Actions have type + owner sense. Done requires an approved artifact path, not a chat summary alone.
