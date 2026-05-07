---
name: 1c-memory-prompter
description: "Generates 5-7 customized memory mining prompts beyond vanilla ChatGPT memory import covering offer deep-dive, communication style, customer conversations, sales history, operating preferences, and network. Two-stage skill - prompt generation instant and extraction async when customer drops LLM dumps. Use when user runs /onboarding-memory or after 1b source extraction completes."
version: 0.1.0
---

# 1c-memory-prompter (Sub-step 1.C)

**Status:** v0.1 BUILT
**Spec:** `phases/phase-1-input-capture-brd.md` Section 5.3

## Two-Stage

**Stage A (instant):** Read `_first-input-layer.md` + `persona-and-priority.md`. Identify gaps. Generate 5-7 customized prompts (offer deep-dive, communication style, customer conversations, sales history, operating preferences, network, persona-specific). Customize per brand/founder/persona/language. Output: `0-Input/memory-extracts/_prompts-to-run.md`.

**Stage B (async):** When customer drops `references/llm-extracts/*.md`, classify each, extract structured signals, dedup against 1b sources, write `0-Input/memory-extracts/<topic>-extract.md` (4-7 files).

## Async Timeout

10 days. Reminders day 3, 7, 10 via Telegram. After 10d: skip-with-gap, mark Class B.

## Self-score

≥9.0 per extract. Min 4 of 7 topics populated. Weighting: Specificity 1.5x, Evidence 1.5x, Differentiation 1.5x, MENA-fit 1.5x.

## Anti-Patterns

1. Don't generate English prompts if customer pref is Arabic
2. Don't make generic prompts (must reference brand/offer/persona)
3. Don't fabricate extracts
4. Don't block phase if only 4/7 topics done
5. Don't double-count signals from 1b

## Handoff

1e-interview-generator (memory-extracts feed gap detection)
