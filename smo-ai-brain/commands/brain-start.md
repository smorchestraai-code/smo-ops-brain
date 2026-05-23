---
description: "Start brain build. Detects single/multi project, organizes workspace."
---

# /brain-start

Canonical entry for Phase 2. Always present (standard command quartet: start, guide, status, validate).

## Usage

```
/brain-start <customer-folder>
```

## What this command does

1. **Detect project structure:** read persona-and-priority.md. Single project, or multiple sibling projects?
2. **Organize workspace to cater for config:**
   - **Single project:** customer folder = project folder (flat). Brain (About-Me + Project + Config) lands in its `1-ProjectBrain/`.
   - **Multi project:** master folder (customer name) + project subfolders. Each project is self-contained with its own About-Me + Project + Config (3 files) + project-instruction. No shared brain layer; the master folder is organizational only.
3. **Verify Phase 1 locked** for the project(s) being built. If not: exit, tell user to finish onboarding first.
4. **Kick off** `2a-brain-orchestrator` -> full brain build chain (or route via /brain-guide).

## Output

Workspace organized. Phase 2 build started. For multi-project, run once per project (each self-contained).

## Next

`/brain-build <project>` per project, or follow `/brain-guide`.
