# book-skill (Codex / work pack)

**Status:** draft  
**Portable:** yes (work-safe when destination is Work-Mind / work project paths)

Compile a **local** technical PDF/EPUB into an on-demand skill pack: small index + chapter files loaded only when relevant.

Full procedure and hard stops: AI-Mind-Vault `Skills/Custom/book-skill.md`.  
Pack layout: `templates/Book-Skill-Pack.md`.

## When to use

- User has a local technical book path and wants reusable agent residue
- Work technical handbooks → **Work-Mind** (or work project `knowledge/books/`) only
- Personal books stay in **My-Mind** (do not copy personal library into this public pack)

## When not to use

- No local file; do not fetch unauthorized copies
- Dumping entire book into context
- Writing book body into pack `core/` or Vault Methodology

## Steps (summary)

1. Confirm path + ownership (work vs personal) + slug  
2. Extract locally  
3. Distill: `SKILL.md`, `chapters/`, `glossary.md`, `patterns.md`, `cheatsheet.md`, `SOURCE.md`  
4. File under Work-Mind (or My-Mind) per Book-Skill-Pack template  
5. Report paths; **single-pass exit** unless user asks to refine  

## Hard stops

| Bound | Default |
|-------|--------|
| Distill passes per invocation | 1 |
| Max chapters per run | 40 |
| Identical extract fail | 1 then escalate |

## Evidence of done

- `SOURCE.md` + pack `SKILL.md` + ≥1 chapter file on disk under the correct Mind root
