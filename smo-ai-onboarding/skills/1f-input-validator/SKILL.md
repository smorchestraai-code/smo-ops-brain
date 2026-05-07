---
name: 1f-input-validator
description: "Validates Phase 1 completeness, runs per-file micro-scoring and phase-level coherence scoring across 7 pairs, then locks Phase 1 or triggers gap-fill loop. Final skill in input capture chain. Requires Telegram operator approval per ADR-001 before lock. Use when user runs /onboarding-validate or after interview completes."
version: 0.1.0
---

# 1f-input-validator (Sub-step 1.F)

**Status:** v0.1 BUILT
**Spec:** `phases/phase-1-input-capture-brd.md` Section 5.6

## Preconditions
1a, 1b, 1c, 1d, 1e all complete (locked or skip-with-gap).

## Four-Stage

**Stage A: Completeness Check** - all required files present.

**Stage B: Per-File Micro-Scoring** - 5-dim rubric on each file. Threshold ≥9.0 per file. MENA-fit floor 8.0.

**Stage C: Phase-Level Macro-Scoring** - 7 coherence pairs (≥9.0 each):
1. 1a persona <-> 1b source signals
2. 1b brand-voice <-> 1c communication-style memory
3. 1b offer-signals <-> 1c offer-extract
4. 1d customer voice files <-> 1b ICP signals
5. 1e interview <-> all prior layers
6. MENA-fit consistency across all files
7. Language consistency across all files

**Stage D: Lock or Loop**
- All pass: lock Phase 1, write _scoring/, update tracker, Telegram operator approval, suggest Phase 2.
- Any fail: identify failed sub-step + dim, generate gap-fill hints, write bridge-plan, suggest re-run.

## Phase Composite
```
phase_composite = weighted_avg(
  completeness * 1.0,
  avg(file_scores) * 1.5,
  avg(coherence_scores) * 2.0,
  min(mena_fit_scores) * 1.0
)
weight_total = 5.5
threshold: ≥9.5
```

## Self-score

Composite ≥9.0. Weighting: Evidence 1.5x, Actionability 1.5x, others 1.0x.

## Anti-Patterns

1. Don't lock if any file <9.0
2. Don't ignore coherence failures
3. Don't lock without Telegram operator approval
4. Don't accept skill self-scores without re-validation
5. Don't skip Stage C even if Stage B passed

## Handoff

Phase 2 brain-orchestrator.
