# Recommended Residue Structure

For any non-trivial Codex / agent session, externalize state into durable files so work compounds and survives context loss.

## Minimal Set
- `PLAN.md` — goal, topology/Diamond, success criteria
- `STATUS.md` — current state, next actions, blockers
- `EVIDENCE.md` or `research/` folder — findings with sources
- `DECISIONS.md` — key choices + rationale
- `REVIEW.md` or `SKEPTIC.md` — verification / adversarial notes

## Naming Conventions
Prefer clear, dated or versioned names when iterating:
- `PLAN-v1.md` → `PLAN-v2.md`
- `EVIDENCE-customer.md`, `EVIDENCE-competitors.md`

## Rule
If it matters, write it to a file. Chat is ephemeral; residue is the real memory.
