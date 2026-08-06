# Diagram Principles (Architecture Visuals)

Portable rules for drawing agent / system architecture without AI-slop flowcharts.

## Geometry first

| What you are showing | Preferred shape |
|----------------------|-----------------|
| Containment / scope (INNER ⊂ MID ⊂ OUTER) | **Nested** shells or concentric regions |
| Stacked abstractions (Harness / Loop / Graph / Eval) | **Layer stack** |
| Decision / W-spine process | **Flowchart** (spine only) |
| Reinforcing improvement cycle | **Loop / flywheel** (+ hub for Probe Ledger) |
| Components + connections | **Architecture** |
| Time-ordered agent messages | **Sequence** |
| Cross-agent handoffs by owner | **Swimlane** |

**Do not hybridize.** Process + containment + eval in one poster muddies the geometry. Prefer overview + detail.

## Density and deletion

- Target density **4/10**. Above ~9 nodes → split.
- Highest-quality move is usually **deletion**.
- Accent / focal highlight on **1–2** elements max.
- Every connection must carry information; if layout already shows the relationship, drop the line.

## Anti-patterns

- Mermaid-default look (stadium nodes, random colors, shadows)
- Cyan/purple glow as “technical”
- Identical boxes for every node (no hierarchy)
- Legend colliding with the drawing
- Diagonal spaghetti when orthogonal elbows would work
- Vertical text on arrows

## AI Mind mapping

| Concept | Type |
|---------|------|
| INNER ⊂ MID ⊂ OUTER | Nested |
| HLG + Eval | Layer stack |
| W0–W7 | Flowchart spine |
| RAI / probes | Loop |
| Diamond research path | Sequence or compact Architecture |
| Handoff | Sequence / Swimlane |

Draw topology **before** automating (Start Manual → Validate → Automate). Whiteboard, Excalidraw, or markdown are all fine — the geometry rules stay the same.
