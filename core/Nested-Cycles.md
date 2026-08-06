# Nested Cycles

HLG is not three parallel checklists. It is a **recursive stack**: the same loop anatomy runs at different grains; graphs compose loops; harness wraps everything; outer cycles treat mid systems as the thing under test.

Mental model: **Environment → Feedback → Flow**  
Grain model: **Inner → Mid → Outer**

---

## Three cycle grains

```
OUTER  (meta / improvement)
  RAI · ops review · probe suite batch
  └── evidence = Probe Ledger, metrics, residue diffs
        │
MID    (job / workflow)
  Graph stages or single qualified loop
  └── each node is an inner loop (or human gate)
        │
INNER  (agent turn)
  model → tools → observe → stop on evidence
  └── harness supplies tools, state, budgets, gates
```

| Grain | What one cycle is | Typical evidence | Typical stop |
|-------|-------------------|------------------|--------------|
| **Inner** | One agent turn / tool sequence | Tool output, test, schema | Success evidence, max retries, budget |
| **Mid** | One job through a pipeline or Diamond | Stage residue (PLAN, Handoff) | Gate pass/fail, human approval |
| **Outer** | Improve or audit the mid system | Probe Ledger, rates | All probes PASS, review done |

**Same seven loop fields at every grain:** Trigger · Goal · State · Action · Evidence · Feedback · Stop.

Declare grain on every filled loop: `Grain: inner | mid | outer`.

---

## How layers nest

```
Harness                    ← environment for all grains
├── tools, permissions, persistence, budgets, observability
├── OUTER loop (optional)
│   └── treats MID system as target under test
├── MID graph or loop
│   ├── node = INNER loop or human gate
│   └── residue edges = shared state
└── INNER may call tools that are tiny graphs
```

1. Harness wraps all grains.
2. Graph node ≈ inner loop (or deterministic / human).
3. Residue flows upward; outer never depends on chat alone.
4. Budgets cascade: outer → mid → inner.
5. Human gates are mid stopping rules.

---

## Promotion rules

| From | To | Only when |
|------|----|-----------|
| Single inner loop | Mid graph | Qualifying Test met |
| Mid pipeline | Dynamic board | Work discovers/cancels tasks mid-run |
| Ad-hoc mid | Outer RAI / review | Spec + Probe Suite needed |
| One agent | Second agent | Pre-split test passes |

Default: **smallest grain that still yields evidence-backed done.**

---

## Residue between grains

| Boundary | What crosses |
|----------|--------------|
| Inner → Mid | Durable artifact for next stage |
| Mid → Mid | Handoff envelope (intent, decisions, artifacts, **ruled-out paths**, next action) |
| Mid → Outer | Metrics / ledgers — not narrative status |
| Outer → Mid | Updated spec, probes, policy as residue |

---

## Failure diagnosis

Name **layer** (Harness / Loop / Graph / Eval) **and grain** (inner / mid / outer).

Do not rewrite outer because an inner loop lacked a stop rule.

---

## Ship checklist

- [ ] Each loop declares grain
- [ ] Each mid stage has residue out
- [ ] Budgets cascade
- [ ] Human gates as mid stop rules
- [ ] Qualifying Test before multi-node graph
- [ ] Outer has Probe Ledger or equivalent
- [ ] Failure names layer **and** grain
