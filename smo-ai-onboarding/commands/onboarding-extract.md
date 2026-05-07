---
description: "Manual scrape URLs and run 5 classifiers (1b)."
---

# /onboarding-extract

Manual trigger for Sub-step 1.B (source extraction).

Invokes the `1b-source-extractor` skill. Reads URLs from `0-Input/persona-and-priority.md`, scrapes each, runs 5 information-target classifiers, writes structured outputs.

See `phases/phase-1-input-capture-brd.md` Section 5.2 and `skills/1b-source-extractor/SKILL.md`.
