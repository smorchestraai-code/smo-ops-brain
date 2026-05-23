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
2. **Organize workspace by altitude:**
   - **Single project:** customer folder = project folder (flat). The whole brain (About-Me + Project + Config incl. the 3 config files + project-instruction) lands in `1-ProjectBrain/`.
   - **Multi project:** master folder (customer) + project subfolders. The 3 config files (profile-settings, cowork-instructions, language-preferences) hoist to `<Customer>/_customer/Config/` (founder's ONE global cockpit identity). Everything else (About-Me, Project, project-instruction) stays per-project.
3. **Verify Phase 1 locked** for the project(s). If not: exit, tell user to finish onboarding first.
4. **Kick off** `2a-brain-orchestrator` -> full brain build chain (or route via /brain-guide).

## Output
Workspace organized by altitude. Phase 2 build started.

## Next
`/brain-build <project>` per project, or follow `/brain-guide`.
