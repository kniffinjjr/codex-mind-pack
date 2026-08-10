# Knowledge Structure Choices

Work-safe mirror of AI Mind Vault `Methodology/Knowledge-Structure-Choices.md`.

**Doctrine in this pack. Instance extracts under `{PROJECTS_DIR}/<slug>/knowledge/` only.**

## Split

| Surface | Holds |
|---------|--------|
| Pack `core/` | Structure ladder, hypergraph rules |
| `{PROJECTS_DIR}/<slug>/` | Actual extracts |

## Structure ladder

| Level | Use when |
|-------|----------|
| Chunks / vector RAG | Single-hop facts, FAQ |
| Lists / Pydantic | Typed fields |
| Binary knowledge graph | Pairwise multi-hop |
| Hypergraph | Native arity >= 3; joint meaning lost if split |
| Temporal / spatial | When / where first-class |

Agent HLG graphs are not knowledge graphs.

## Hypergraph

Binary edge: 2 entities. Hyperedge: n >= 2 in one relation.
Use only when `templates/Hypergraph-Entry-Criteria.md` passes.
Pipeline: sources -> gate -> extract -> project knowledge/extract/ -> retrieve.
Sources remain truth; extract is rebuildable residue.

## Project layout

```text
{PROJECTS_DIR}/<slug>/
  Overview.md
  knowledge/
    sources/
    extract/README.md
```

Do not store instance graphs in core/. Prefer simplest structure that answers the questions.
