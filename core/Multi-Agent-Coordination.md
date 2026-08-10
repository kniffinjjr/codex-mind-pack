# Multi-Agent Coordination

Work-safe mirror of Vault Process/Multi-Agent-Coordination.md.

**Problem:** Parallel agents + GitHub tools -> false already-completed, missing commits.
**Principle:** Boards are voluntary. Match coordination to the runtime.

## Two runtimes

| | Web Grok (<=4 agents) | Grok Build |
|--|----------------------|------------|
| Control | Sole writer + STAND DOWN + SHA verify | One owner per job/branch |
| Failure | Tool dedupe, no commit | Branch/workspace conflicts |

## Web team

- Leader = sole writer on pack/shared docs unless user names another.
- Specialists = research, draft, verify SHA — no push_files on contended repos.
- After every write: confirm commit SHA. Never trust "another agent already completed" alone.

```
SOLE_WRITE | repo: ... | paths: ... | others STAND DOWN
-> write -> confirm SHA -> DONE
```

## Grok Build

- One agent owns the branch for the job.
- Feature branch + PR for app code.
- Pack/Vault via GitHub MCP -> same sole-writer + SHA rule.

## Parallel vs serial

| Parallel OK | Serial only |
|-------------|-------------|
| Reads, analysis, drafts | GitHub writes same repo/path |
| SHA verify | Everyone finish same commit |

Chatroom STAND DOWN is the real control on Web Grok; WRITE_QUEUE is advisory unless agents obey.
