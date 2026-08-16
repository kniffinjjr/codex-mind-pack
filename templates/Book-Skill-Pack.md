# Book Skill Pack — Layout Template

**Purpose:** Standard folder layout for one technical book (or multi-file source set) compiled into an on-demand agent skill pack.

**Ownership (work pack)**

| Book type | Root |
|-----------|------|
| Work / company | `{WORK_MIND_ROOT}/Projects/<library-or-project>/knowledge/books/<slug>/` |
| Personal | `{MY_MIND_ROOT}/...` (My-Mind only — not filed into this public pack) |

Do **not** place generated book body under pack `core/` or Vault `Methodology/` / `Concepts/`.

Related skill: `Skills/book-skill.md`. Full Vault overlay: AI-Mind-Vault `Skills/Custom/book-skill.md`.

---

## Directory tree

```text
knowledge/books/<slug>/
  SKILL.md              # Always-on index (~3–4k tokens target)
  SOURCE.md             # Original path, date, license note, extractor
  glossary.md           # Terms + chapter refs
  patterns.md           # Techniques / algorithms / design patterns
  cheatsheet.md         # Decision tables / quick rules
  chapters/
    ch01-<short-title>.md
    ch02-<short-title>.md
    ...
```

`<slug>` = lowercase kebab-case from title or user.

---

## File specs

### SKILL.md (pack index)

1. Book title + author (if known)
2. One-paragraph thesis
3. 5–12 named frameworks / mental models (author’s terms)
4. Chapter index: `chNN | title | when to load`
5. Example asks (“load ch05”, “replication from this book”)
6. Note that full prose lives in `chapters/` — do not paste whole book into chat

### SOURCE.md

| Field | Content |
|-------|--------|
| Original path | Absolute path at extract time |
| Extracted | ISO date |
| Tool / method | e.g. pdftotext, Docling, manual |
| License / ownership | work-licensed \| personal copy \| note |
| Mind | Work-Mind \| My-Mind |

### chapters/chNN-*.md

- Target ~800–1200 tokens each
- Frameworks, decision rules, anti-patterns, worked examples
- Optional page/section refs
- Not a full verbatim chapter dump

---

## Verify checklist

- [ ] `SOURCE.md` present
- [ ] Pack `SKILL.md` has thesis + chapter index
- [ ] At least one `chapters/ch*.md` file
- [ ] Correct Mind root (work vs personal)
- [ ] No book body in pack `core/` or Vault controlling docs

---

## Change log

- 2026-08-16: Initial (synced from AI-Mind-Vault Book-Skill-Pack).
