---
# Copy into: {PROJECTS_DIR}/<slug>/Overview.md
# Work Mind only — do not use this template for personal My-Mind notes.

type: project
tags:
  - project
  - work
title: "{{Project display name}}"
status: active          # active | blocked | paused | complete
priority: medium        # critical | high | medium | low
category: engineering   # district label — engineering | analytics | ops | product | other
stage: active           # backlog | active | paused | complete
projectDir: ""          # REQUIRED: absolute path to work repo/folder for agent launch
stack: []               # e.g. [python, typescript, solidworks]
health: 70              # 0–100 optional
scope: 1                # optional footprint hint
questions: []           # open quests (optional)
answered: []            # resolved quests (optional)
blocked_by: []          # optional [[Other Project]] or titles
depends_on: []          # optional
no_deps: false
---

# {{Project display name}}

**Slug:** `<slug>`  
**Mind:** Work-Mind  
**Code / working directory:** see `projectDir` in frontmatter

## Purpose

-

## Current focus

-

## Links

- Knowledge extracts: `./knowledge/extract/`
- Lessons: `./Lessons-Learned.md` (if any)

## Notes

Hypervault reads this frontmatter to place a building (color=status, height=priority, district=category). Launch agent uses `projectDir` only — keep it on the corporate machine path.
