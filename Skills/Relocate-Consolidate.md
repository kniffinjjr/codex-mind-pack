# Relocate & consolidate existing SKILLS.md files

Use this when a machine, project, or older AI Mind layout already has skill catalogs that should fold into the Codex Mind Pack map (and, when appropriate, the private Vault).

**Canonical pack surface after consolidation**

| Artifact | Path |
|----------|------|
| Routing map | `{PACK_ROOT}/Skills/Agent-Skill-Map.md` |
| This procedure | `{PACK_ROOT}/Skills/Relocate-Consolidate.md` |
| Personalities (paste packs) | `{PACK_ROOT}/personalities/` |
| Optional local runtime bodies | Agent skill dirs (e.g. `SKILL.md` per skill) — not duplicated as monorepo doctrine |
| Full private catalog | AI-Mind-Vault `Skills/` (approval-gated) |

There is **no** single required root file named `SKILLS.md` in this pack. Prefer the map + personalities + local/Vault skill bodies.

---

## 1. Discover

Search common locations (adjust for `PATHS.md`):

```text
{PACK_ROOT}/SKILLS.md
{PACK_ROOT}/skills.md
{PACK_ROOT}/Skills.md
{PROJECTS_DIR}/**/SKILLS.md
{PROJECTS_DIR}/**/skills.md
~/Documents/**/SKILLS.md
# Agent runtime catalogs (examples — platform-specific)
~/.codex/**/skills*
~/.grok/skills/**/SKILL.md
```

Also check chat exports, Drive “AI Mind” folders, and any single-file registries that list skills inline.

Record each hit: path, approximate size, last modified, whether it looks like a **catalog**, a **paste pack**, or a **full procedure body**.

---

## 2. Classify (before moving anything)

| Class | Meaning | Default destination |
|-------|---------|---------------------|
| **A. Work routing** | Persona → skill tables, cluster lists, “when to use” | Merge into `Skills/Agent-Skill-Map.md` |
| **B. Work personality / short pack** | ≤4k paste instructions for Codex/GPT work agents | `personalities/<Name>.md` (or update existing) |
| **C. Work operational body** | Full SKILL.md procedure used at runtime | Keep in agent skill directory; **link** from the map — do not paste full body into the public pack unless user asks |
| **D. Personal / domain-only** | Investing, tax, RE, recruiter, SmaRV, PDM, Grok-named personal agents | Private Vault only (`Skills/Custom/`, Short-Instructions, Agent-Skill-Map) via **REVIEW_QUEUE** |
| **E. Project residue** | One-off project skill lists, experiments | `{PROJECTS_DIR}/<slug>/` — do not promote to pack map without review |
| **F. Duplicate / obsolete** | Same doctrine under two names | Keep one map name; tombstone the other |

**Rules**

1. Personality ≠ skill — do not merge paste packs into the map as if they were procedures.
2. No double doctrine — if two files teach conflicting rules for the same domain, stop and ask the user.
3. Public pack stays work-safe — personal catalogs never land in `codex-mind-pack` origin.
4. Vault permanent notes need user approval; pack map edits are pack git under user direction.

---

## 3. Consolidate (work-safe path)

For each **Class A** item:

1. Diff against current `Skills/Agent-Skill-Map.md`.
2. Add missing rows / cluster entries; do not rename established skill ids without user OK.
3. Note source path in the commit message or a short “Sources merged” footnote at the bottom of the map (optional).

For each **Class B** item:

1. Compare to `personalities/`.
2. Update or add a neutral-named pack; strip Grok-only branding if publishing in this pack.
3. Ensure `personalities/README.md` and the map still agree.

For each **Class C** item:

1. Leave runtime `SKILL.md` where the agent host expects it (or record path in local `PATHS.md` if you introduce a `SKILLS_RUNTIME` key).
2. Ensure the map names the skill id agents should call.

For **Class D**:

1. Draft Vault proposal only (`Drafts/` or `_meta/REVIEW_QUEUE.md`).
2. Do not push personal skill catalogs to this public repo.

For **Class E**:

1. Move under the project slug if worth keeping.
2. Promote to pack map only after explicit user direction.

---

## 4. Relocate & tombstone

After content is merged:

1. **Remove or replace** the old root `SKILLS.md` / `skills.md` so agents do not treat it as authoritative.
2. Preferred tombstone (leave a stub at the old path if other tools still open it):

```markdown
# SKILLS.md (moved)

This catalog was consolidated into the Codex Mind Pack:

- Routing: `{PACK_ROOT}/Skills/Agent-Skill-Map.md`
- Procedure: `{PACK_ROOT}/Skills/Relocate-Consolidate.md`
- Personalities: `{PACK_ROOT}/personalities/`

Do not edit this stub. Update the map instead.
```

3. Commit pack changes on `codex-mind-pack` (architecture). Do not commit secrets or personal residue.
4. If the old file lived only on a work machine, local delete + git pull of the pack is enough.

---

## 5. PATHS (optional runtime root)

If skill **bodies** live outside the pack, document them in local `PATHS.md` (gitignored):

```markdown
PACK_ROOT: ...
PROJECTS_DIR: ...
# Optional — agent host skill directories (not committed)
SKILLS_RUNTIME: ~/.grok/skills
# or: D:/Work/agent-skills
```

Agents that need a full procedure body resolve `SKILLS_RUNTIME/<skill-id>/SKILL.md` (or platform equivalent) after reading the pack map. The map remains the **routing** source of truth for this pack.

---

## 6. Checklist (agent or human)

- [ ] Discovery list complete (pack root, projects, home, agent skill dirs)
- [ ] Each file classified A–F
- [ ] Map updated for work routing only
- [ ] Personalities updated if short packs changed
- [ ] No personal/domain catalogs pushed to public origin
- [ ] Vault proposals filed for Class D permanent notes
- [ ] Old `SKILLS.md` removed or tombstoned
- [ ] `git status` clean of secrets; pack commit under user direction

---

## 7. When in doubt

- Call **Librarian** for path orientation; **Page Master** for map/doc edits.
- Prefer merging into `Agent-Skill-Map.md` over creating a second root catalog.
- Never invent a parallel `SKILLS.md` as the long-term pack standard.
