---
description: "Build customer business brain from Phase 1 inputs (Phase 2)."
---

# /brain-build

Full Phase 2 build chain. (Canonical entry is /brain-start, which organizes the workspace first.) Generate the customer's business brain (`1-ProjectBrain/`) from the locked Phase 1 `0-Input/` + `references/`.

## Usage

```
/brain-build <customer-folder>
```

## Preconditions

- Phase 1 locked (0-Input/ at Class A, _progress.md shows Phase 1 locked)
- If not locked: exit, tell user to finish onboarding first

## What this command does

1. Invokes `2a-brain-orchestrator` (reads inputs, detects persona + complexity, plans brain file set)
2. Chains 2b-about-me-builder, 2c-project-builder, 2d-config-builder
3. Runs 2e-brain-scorer per file
4. Runs 2f-brain-validator (coherence + Phase 1 alignment, locks Phase 2)

## Output

`<customer-folder>/1-ProjectBrain/` populated at Class A (About-Me + Project + Config).

## Next

After Phase 2 locks, customer brain is ready to load into their Claude cockpit. Proceed to Phase 3 (GTM strategy) when built.
