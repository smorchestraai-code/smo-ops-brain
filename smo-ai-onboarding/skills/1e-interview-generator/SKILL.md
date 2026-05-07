---
name: 1e-interview-generator
description: "Generates gap-driven interview questions and tools inventory after 1c and 1d both complete. Three-stage skill - gap detection, capture (async or recorded call), and tools inventory deep-dive across 12 categories. Use when user runs /onboarding-interview or after both memory mining and files request lock."
version: 0.1.0
---

# 1e-interview-generator (Sub-step 1.E)

**Status:** v0.1 BUILT
**Spec:** `phases/phase-1-input-capture-brd.md` Section 5.5

## Preconditions
- 1c locked (memory extracts ≥9.0)
- 1d locked (files ≥80% received OR explicit signal)

## Three-Stage

**Stage A (instant):** Read all prior layers. Run gap detector against 10 brain dimensions (4 About-Me + 6 Project). Generate 1-3 questions per <9.0 dimension + 12-question tools inventory. Output: `0-Input/interview-gaps.md`.

**Stage B:** Capture answers. Async mode: founder fills form. Call mode: team-recorded call (Otter/Fathom), transcript dropped to `references/interview-recordings/`. Call timeout: 5 days, then revert to async. Async mode: no timeout, reminders day 7 + 14.

**Stage C:** Tools inventory deep-dive (12 categories: CRM, email infra, email marketing, LinkedIn, ads, scraping, AI agents, video, design, scheduling, payments, analytics).

## Self-score

≥9.0 on interview-gaps.md AND tools-inventory.md. Weighting: Actionability 2.0x, Specificity 1.5x, Differentiation 1.5x, MENA-fit 1.5x, Evidence 1.0x.

## Anti-Patterns

1. Don't ask questions already answered by 1b/1c/1d
2. Don't ask vague questions
3. Don't proceed without all 12 tool categories
4. Don't ignore conflict flags from 1b
5. Don't accept hand-wavy answers
6. Don't translate transcript to English if founder spoke Arabic

## Handoff

1f-input-validator
