# Agent ↔ Skill Map (Codex / GPT work pack)

**Personalities** = paste packs under `personalities/` (instruction surface).  
**Skills** = operational procedures (local `SKILL.md` bodies and/or Vault `Skills/Custom/` overlays when reachable).

This map is the portable, work-safe subset of the private AI-Mind-Vault skill routing. It does not replace `AGENTS.md`.

**Existing catalogs:** If you still have root or project `SKILLS.md` / `skills.md` files, fold them in using **`Skills/Relocate-Consolidate.md`** (discover → classify → merge → tombstone). Do not maintain a second root catalog alongside this map.

---

## Pack personalities → primary skills

| Personality (this pack) | Primary skill(s) | Supporting |
|-------------------------|------------------|------------|
| **Librarian** | `grokrarian` (pack: orient against pack files + PATHS) | Page Master |
| **Page Master** | `page-master` | Librarian, diagram-design |
| **Lessons Learned** | `lessons-learned` | Page Master, Librarian |
| **Accountant** | `accountant` | — |
| **PHD Researcher** | `first-principles-research` | Librarian, Page Master |
| **Code Architect** | coding / architecture practice (no single named skill file in pack) | react-ui, nextjs-app, eval-engineering |
| **Forge Hardware** | `hardware-forge` | strategic-buyer (Vault), kicad / smarv (Vault) |
| **FDE** | `fde` | harness-loop-graph, eval-engineering |

Load **one** personality pack at a time. Skills still obey `AGENTS.md` (HLG, residue, Writer ≠ Checker, PATHS, git gate).

---

## Cross-cutting (any agent)

| Skill | Use |
|-------|-----|
| `harness-loop-graph` | **Architecture / design / diagnosis only.** Agent architecture: Harness · Loop · Graph. Activate only on explicit design/review/debug of agentic systems. Do **not** auto-apply to ordinary coding, simple Q&A, or routine turns — the detailed hard-stop contract is skill-session only. |
| `eval-engineering` | Probes, RAI, verdicts that change the next edge |
| `diagram-design` | Architecture / workflow visuals (HTML+SVG) |
| `fde` | Ship persistent, auditable production tools |
| `accountant` | Tokens → credits → USD; project ledgers |
| `lessons-learned` | After-action on complete or major revision |
| `page-master` | Guides, runbooks, short instruction packs |
| `grokrarian` / Librarian | Orient, locate, route knowledge; PATHS hygiene |

---

## Website design cluster (any agent)

| Skill | Use |
|-------|-----|
| `landing-page` | Conversion pages, hero / proof / CTA hierarchy |
| `product-page` | PDP / ecommerce product pages, offer stack, upsells |
| `design-system` | Tokens, type, components, themes |
| `site-ia` | Sitemap, nav, page types, URLs |
| `responsive-shell` | Mobile-first shells and grids |
| `a11y-build` | Accessible implementation patterns |
| `form-ux` | Forms and multi-step flows |
| `web-motion` | Purposeful micro-interactions |
| `seo-page` | Intent, titles, heading structure |
| `better-interface` | Holistic UI review / polish |
| `pixelslop` | AI-generic design QA |

**Design → implement pipeline:**  
`site-ia` → `design-system` → `responsive-shell` → `landing-page` / `product-page` / `form-ux` → `react-ui` / `nextjs-app` → `a11y-build` → `web-motion` → `seo-page` → `better-interface` + `pixelslop`.

---

## Web implementation cluster (any agent)

| Skill | Use |
|-------|-----|
| `react-ui` | React components, hooks, TypeScript props, composition |
| `nextjs-app` | App Router, RSC vs client, layouts, metadata, data / caching |

---

## Not in this pack (private Vault / personal only)

| Area | Examples |
|------|----------|
| Personal finance / markets | fiduciary-investor, options / day-trader skills |
| Tax / real estate | worlds-best-cpa-tax-attorney, tx-fl-real-estate |
| Buying / sourcing | strategic-buyer (full GrokDeals surface) |
| Domain product ops | solidworks-pdm-automation, smarv-platform, kicad-ai-agent, worlds-greatest-recruiter |
| Grok-only catalogs | Grok-Agent-Personalities, full Short-Instructions for personal agents |

When those are needed, use the private Vault (and its approval gate). Do not fork them into this public pack.

---

## Design rules

1. **Personality ≠ skill.** Paste packs set tone and triggers; skills define operational procedure.
2. **No double doctrine** across domain boundaries (e.g. Elite Trader ≠ Fiduciary Investor).
3. **New portable skill:** add a short instruction block (when maintained for Codex) **and** a row in this map. Full runtime body may live in local `SKILL.md` or Vault `Skills/Custom/`.
4. **Vault permanent skill notes** still require REVIEW_QUEUE + explicit user approval. Pack map updates are pack architecture (git on this repo under user direction).
5. Prefer existing map entries over inventing parallel skill names.
6. **No parallel root `SKILLS.md`.** Relocate/consolidate per `Skills/Relocate-Consolidate.md`.

---

## Maintenance

- **Owner (pack):** Page Master + Librarian when updating the portable map.
- **Source of truth for full skill set:** private AI-Mind-Vault `Skills/Agent-Skill-Map.md` + `Skills/Custom/`.
- After approved Vault skill changes that affect work surface, sync this file (Vault → pack) on user request.
- When absorbing legacy catalogs, follow `Skills/Relocate-Consolidate.md` and tombstone old paths.
