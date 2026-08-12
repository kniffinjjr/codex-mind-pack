# Run Knowledge Extract (work-safe)

**Purpose:** After a meaningful agent run, leave durable linked residue so the next run does not start from a session trash can.

**Instance path (Work Mind only for company work):**

```text
{WORK_MIND_ROOT}/Projects/<slug>/knowledge/extract/
  YYYY-MM-DD-<short-slug>.md
  README.md
```

Do **not** copy work extracts into the portable Vault or personal My-Mind.

Full doctrine: upstream AI Mind Vault `Templates/Run-Knowledge-Extract.md` + `Methodology/Knowledge-Structure-Choices.md`.

---

## When to fill

Multi-source research, multi-agent analysis, design reviews with lasting claims. Skip pure ephemeral chat.

---

## Template

```markdown
---
project: <slug>
mind: Work-Mind
date: YYYY-MM-DD
run_type: research | multi-agent | design | other
sources: []
structure: binary-graph | hypergraph | lists | mixed
---

# Extract — <topic> — <YYYY-MM-DD>

## Context
- Goal:
- Prior extracts:

## Nodes
| id | type | claim / label | source | confidence |
|----|------|---------------|--------|------------|
|    |      |               |        |            |

## Edges
| from | relation | to | evidence | note |
|------|----------|----|----------|------|
|      |          |    |          |      |

## Open / contradictions
-

## Hubs / single points of failure
-

## Next questions
-
```

## Minimal

```markdown
# Extract — <topic> — <date>
**Project:** <slug> | **Mind:** Work-Mind
**Nodes:** …
**Edges:** A → relation → B (evidence)
**Open / Next:** …
```

## Process

1. Write extract under Work-Mind project path.  
2. Next run **loads extract first**.  
3. Hypergraph only if entry criteria pass (`templates/Hypergraph-Entry-Criteria.md`).  
