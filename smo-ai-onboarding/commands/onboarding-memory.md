---
description: "Manual generate memory prompts and extract dumps (1c)."
---

# /onboarding-memory

Manual trigger for Sub-step 1.C (memory mining).

Invokes the `1c-memory-prompter` skill. Stage A generates customized prompts informed by the first input layer. Stage B parses raw LLM dumps in `references/llm-extracts/` and structures them.

See `phases/phase-1-input-capture-brd.md` Section 5.3 and `skills/1c-memory-prompter/SKILL.md`.
