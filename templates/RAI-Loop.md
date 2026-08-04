# RAI Loop — Executable Steps for Codex / Coding Agents

Use this when hardening an agent (or this mind-pack itself) before deploy.

## Steps

1. **Load the spec**  
   Read `AGENTS.md` and any project-specific instructions that define correct behavior.

2. **Load or derive the Probe Suite**  
   Start with `templates/Probe-Suite.md`. Add any probes that came from real failures.

3. **Run the suite**  
   For each probe: execute the scenario against the target (or against the instruction surface). Record PASS / FAIL + short evidence.

4. **Edit one lever at a time**  
   For each FAIL: choose the smallest change (tighten a rule, add a sentence, adjust a tool policy). Do not rewrite everything.

5. **Re-run only failures + spot-checks**  
   Confirm the fix. Then spot-check previously passing probes for regressions.

6. **Write residue**  
   Update the LEDGER section (or a `LEDGER.md`) with before/after and the exact change made.

7. **Stop when clean**  
   All probes PASS, or remaining FAILs are explicitly escalated with residue.

## Stopping Rules

- Success = every probe PASS
- Max edit cycles per probe ≈ 3–5
- Budget / time ceiling → stop and surface open items
- Missing harness surfaces (no way to test) → fail the loop and report what is missing

## Notes

- Prefer convergent RAI (toward the written spec) over open-ended self-improvement.
- Never accept “I am confident it is fixed” without re-running the failing probe.
- The Probe Ledger is first-class residue.
