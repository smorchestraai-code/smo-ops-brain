---
name: 2f-brain-validator
description: "Validates brain coherence and faithfulness to Phase 1 inputs, then locks Phase 2 or triggers gap-fill loop. Checks brain-internal coherence, brain-to-input faithfulness (no drift), sibling About-Me consistency, meta-config hoisting to the customer master, and no business bleed across sibling projects. Requires Telegram operator approval before lock. Use when user runs /brain-validate or after brain scoring."
version: 0.2.0
---

# 2f-brain-validator

**Spec:** `phases/phase-2-brain-context-brd.md`

## Purpose
Final Phase 2 gate. Coherence + faithfulness + lock.

## 4 Stages

**A: Completeness** - all planned files present.

**B: Per-file scores** - every file >=9.5.

**C: Coherence** (7 pairs >=9.0): positioning<->offer, offer<->icp, icp<->gtm-motions, brand-voice<->communication-style, brain<->Phase 1 (faithfulness), goals-and-vision<->project-instruction, MENA-fit+language consistency.

**D: Lock or loop** - all pass -> write _scoring/, update tracker + _progress, Telegram approval, suggest Phase 3. Any fail -> bridge-plan, gap-fill hints, re-run.

## Multi-Project Master Assembly Check
For multi-project customers, additionally verify:
1. About-Me written once to `<Customer>/_customer/About-Me/` (not duplicated per project)
2. Meta-config written once to `<Customer>/_customer/Config/`
3. No drift: founder facts + meta-config identical across project runs
4. project-instruction.md present per project
5. No business bleed: each project's Project/ files contain only that project's business

## Output
- `_scoring/phase-2-scores.md`, `coherence-map.md`, `bridge-plan.md`
- `tracker.md`, `_progress.md` updated
- INPUT-GAP report

## Threshold
Phase composite >=9.5. All coherence >=9.0. Zero business bleed. Zero unresolved hallucination.

## Anti-Patterns
1. Don't lock with any file <9.5
2. Don't lock with business bleed
3. Don't lock with About-Me drift across siblings
4. Don't lock without Telegram approval
5. Don't ignore INPUT-GAPs

## Handoff
Phase 3 (smo-ai-gtm-strategy)
