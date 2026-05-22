---
description: "Build customer business brain from Phase 1 inputs (Phase 2)."
---

# /brain-build

Canonical entry. Generate the customer's business brain (`1-ProjectBrain/`) from the locked Phase 1 `0-Input/` + `references/`.

## Usage

```
/brain-build <customer-folder>
```

## Preconditions

- Phase 1 locked (0-Input/ at Class A, _progress.md shows Phase 1 locked)
- If not locked: exit, tell user to finish onboarding first

## What this command does

1. Invokes `2a-brain-orchestrator`
2. Chains 2b-about-me-builder, 2c-project-builder, 2d-config-builder
3. Runs 2e-brain-scorer per file
4. Runs 2f-brain-validator (locks Phase 2)

## Output

`<customer-folder>/1-ProjectBrain/` populated at Class A.

## Next

After Phase 2 locks, brain ready for the customer Claude cockpit. Proceed to Phase 3 when built.
