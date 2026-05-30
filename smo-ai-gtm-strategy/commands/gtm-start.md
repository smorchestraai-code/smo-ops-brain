---
description: "Start GTM strategy build. Detects single/multi project."
---

# /gtm-start

Canonical entry for Phase 3.

## Usage
```
/gtm-start <customer-folder>
```

## What this command does
1. Read persona-and-priority.md. Detect single project or multiple sibling projects.
2. Verify Phase 2 brain locked for the project(s). Exit if not.
3. Organize `2-GTM/` workspace per project.
4. Kick off `3a-gtm-orchestrator` -> full Phase 3 chain.

For multi-project: run sequentially per project. Each project gets its own playbook + assets + deployment.
