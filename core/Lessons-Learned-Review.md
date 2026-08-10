# Lessons Learned Review

**Purpose:** Capture actionable lessons when a project completes or after a major revision, so the system compounds instead of repeating the same failures.

Outer Nested Cycle residue. Human review gates permanent commits.

## When to run

| Trigger | Example |
|---------|--------|
| Project complete / shipped | Feature done, migration finished, handoff |
| Major revision | Architecture pivot, abandoned approach, large refactor |
| Production incident / costly failure | After recovery, before “move on” |
| Explicit ask | lessons learned, postmortem, close out |

## Loop

```
Scope → Gather → Extract → Classify → Draft → Human review → Commit
```

1. **Scope** — Project slug, `{PROJECTS_DIR}`, complete vs revision, time window.
2. **Gather** — Evidence only: decisions, failures, costs, handoffs, races, user corrections.
3. **Extract** — Actionable lessons, not vibes.
4. **Classify**
   - **Local** — this project / work-IP only
   - **Portable** — process or methodology any pack adopter could reuse
5. **Draft** — `templates/Lessons-Learned.md`
6. **Human review** — Approve, edit, or reject. Portable pack-architecture changes never auto-merge.
7. **Commit**
   - Local → `{PROJECTS_DIR}/<slug>/Lessons-Learned.md` (append dated section if file exists)
   - Portable → propose change to `core/` or `AGENTS.md` only with explicit user direction

## Filing

| Content | Destination |
|---------|-------------|
| Project lessons | `{PROJECTS_DIR}/<slug>/Lessons-Learned.md` |
| Portable process | Pack `core/` / templates only after user direction |
| Work IP | Stay under project path; do not push private project residue to public origin |

Resolve `PATHS.md` first. See `AGENTS.md` §0 and `GIT.md`.

## Quality bar

- Failures map to mechanism: Harness / Loop / Graph / process / skill gap
- Actions: do more · stop · change · experiment — with owner sense and timing
- Prefer few sharp lessons over long narrative

## Ownership

| Role | Duty |
|------|------|
| **Lessons Learned** personality | Run the loop; draft; commit plan |
| **Page Master** | Optional polish of the written artifact |
| **Librarian** | Path orientation |
| **Human** | Approve commits and portable promotions |
