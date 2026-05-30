---
name: 3h-staged-trigger
description: "Triggers deployed campaigns via staged rollout: test contact (1 internal) then small batch (10% or 50, whichever smaller, 24h observation) then full batch. Auto-progresses if open-rate >= floor AND no bounces > threshold AND no spam reports. Operator can pause any stage via Telegram one-tap. Gates 2 (trigger approval) and 3 (scale approval) per ADR-001. Use after 3g cluster deploys + smoke test passes."
version: 0.1.0
---

# 3h-staged-trigger

**Spec:** `phases/phase-3-gtm-strategy-brd.md` Section 8-9

## Purpose
Trigger campaigns safely. Catch broken sequences before they hit the customer's full list.

## Preconditions
- All 3g cluster complete
- Smoke test passed (1 test contact received deployed sequence, opened, rendered correctly)
- Gate 1 (pack approval) already cleared

## Process

### Stage 0: Smoke Test
1. Send sequence to 1 internal test contact (operator's email, not customer's list).
2. Verify: render, links, personalization, attachments.
3. If pass: surface to Telegram for Gate 2.
4. If fail: alert + pause.

### Gate 2 (Telegram)
- Shown: deploy summary per surface, segment sizes, first-send preview, test result
- Asked: Trigger / Stage 10% / Pause / Reject
- Default after 72h: auto-pause

### Stage 1: Small Batch
1. Trigger sequence to 10% of segment OR 50 contacts (smaller).
2. 24h observation:
   - open_rate >= floor (default 25%)
   - bounces < threshold (default 2%)
   - spam_reports = 0
3. If pass criteria met: auto-progress to Stage 2.
4. If breached: auto-pause + alert.

### Stage 2: Full Batch
1. Trigger to remainder of segment.
2. 48h observation (feeds Gate 3).

### Gate 3 (Telegram)
- Shown: outcome dashboard (open rate, reply rate, conversion if measurable) vs benchmarks + recommendation
- Asked: Expand / Hold / Modify
- Default: Hold (conservative)

## Output
- `2-GTM/output/_trigger/staged-log.md` (timestamps, stage transitions, metrics per stage)

## Self-score
6-dim. Composite >=9.5.

## Anti-Patterns
1. Don't skip smoke test
2. Don't auto-progress past Gate 2 without operator approval
3. Don't skip 24h observation window in Stage 1
4. Don't ignore breached thresholds (auto-pause is mandatory)
5. Don't proceed to Gate 3 without 48h metrics

## Handoff
3i-gtm-validator
