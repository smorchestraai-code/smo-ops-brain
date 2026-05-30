---
name: 3i-gtm-validator
description: "Final Phase 3 gate. Validates per-asset Class A scores, 8 coherence pairs, traceability, no-business-bleed, deployment success, smoke test, gate completion, and outcome floors at Gate 3. Locks Phase 3 or triggers gap-fill loop. Produces _handoff-to-phase4.md schema for the next plugin. Requires Telegram operator approval before lock per ADR-001."
version: 0.1.0
---

# 3i-gtm-validator

**Spec:** `phases/phase-3-gtm-strategy-brd.md` Section 13, 15-16

## Purpose
Final Phase 3 gate. Coherence + traceability + deployment + trigger + handoff.

## 6 Stages

**A: Completeness** - all assets in `2-GTM/output/sequences/`, `funnels/`, `whatsapp/`, `content/` present per `_build-plan.md`.

**B: Per-asset scores** - every asset >=9.5 (from 3f). Brand-voice-fit >=8.5.

**C: Coherence** - all 8 pairs >=9.0 (from 3f1).

**D: Traceability** - zero fabrications, INPUT-GAPs <=5% (from 3f2).

**E: Deployment** - all 7 GHL surfaces deployed, smoke test passed (3g + 3h Stage 0).

**F: Trigger + Outcome** - staged trigger ran through Gate 3, outcome floors met (open rate baseline, bounce floor, no spam).

## Gate
After all 6 stages pass, surface to Telegram per ADR-001 for final operator approval before lock.

## Output
- `2-GTM/output/_handoff-to-phase4.md` (the Phase 4 handoff schema)
- `tracker.md` updated
- `_progress.md` Phase 3 = locked
- `_scoring/phase-3-final.md`

## Self-score
6-dim. Composite >=9.5.

## Anti-Patterns
1. Don't lock with any asset <9.5
2. Don't lock with any coherence pair <9.0
3. Don't lock with any fabrication
4. Don't lock without Telegram approval
5. Don't omit Phase 4 handoff schema

## Handoff
Phase 4 (smo-ai-brd, next plugin)
