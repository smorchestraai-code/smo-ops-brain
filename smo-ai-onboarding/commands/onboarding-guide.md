---
description: "Copilot. Detects active phase and recommends next."
---

# /onboarding-guide

Copilot. Reads tracker.md, recommends next action.

## Usage

```
/onboarding-guide <customer-folder>
```

## What it does

1. Read `<customer-folder>/tracker.md`
2. Identify Active Phase + last sub-step state
3. Per Phase 1 BRD Section 4.4, determine next action

See `phases/phase-1-input-capture-brd.md` Section 4.4 for orchestration logic.
