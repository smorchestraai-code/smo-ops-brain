---
name: 1d-files-requester
description: "Generates customized file request list per persona (SaaS, Pro Services, Enterprise, Ecom) and processes files when customer drops them via docx, pdf, pptx, xlsx skills. Two-stage skill - list generation instant and file processing async. Use when user runs /onboarding-files or after 1b source extraction completes."
version: 0.1.0
---

# 1d-files-requester (Sub-step 1.D)

**Status:** v0.1 BUILT
**Spec:** `phases/phase-1-input-capture-brd.md` Section 5.4

## Two-Stage

**Stage A (instant):** Generate persona-customized request list. Base + persona variants (SaaS adds product roadmap, churn; Pro Services adds retainers, SOWs; Enterprise adds RFPs, security questionnaires; Ecom adds product catalog, supplier list, fulfillment SOP). Output: `references/files-requested/_request-list.md`.

**Stage B (async):** Per file dropped: extract via docx/pdf/pptx/xlsx skills, classify signals, augment sources. Output: `references/docs/<file>-extracted.md` + `0-Input/sources/<doc>.md`.

## Async Timeout

10 days. Reminders day 3, 7, 10. Threshold: ≥80% Tier 1+2 received OR explicit signal.

## Self-score

≥9.0 per processed file. Weighting: Evidence 1.5x, Actionability 1.5x, MENA-fit 1.5x, others 1.0x.

## Anti-Patterns

1. Don't request files customer already provided in 1b sources
2. Don't request outside persona scope
3. Don't block phase if customer can't provide some
4. Don't extract PII silently
5. Don't strip Arabic content

## Handoff

1e-interview-generator (extracted files feed gap detection)
