---
description: "Manual validate Phase 1, lock or loop (1f)."
---

# /onboarding-validate

Manual trigger for Sub-step 1.F (input validation + Phase 1 lock).

Preconditions: 1a, 1b, 1c, 1d, 1e all complete.

Invokes the `1f-input-validator` skill. Checks completeness, runs per-file micro-scoring and phase-level macro-scoring (coherence), locks Phase 1 if Class A or triggers gap-fill loop.

See `phases/phase-1-input-capture-brd.md` Section 5.6 and `skills/1f-input-validator/SKILL.md`.
