---
name: 2f-brain-validator
description: "Validates per-project brain coherence and faithfulness to Phase 1 inputs, then locks Phase 2 or triggers gap-fill loop. Each project brain is self-contained (About-Me, Project, and 4 config files all project-level). Checks brain-internal coherence (positioning agrees with offer agrees with ICP), brain-to-input faithfulness (no drift), and no business bleed across sibling projects. Requires Telegram operator approval before lock. Use when user runs /brain-validate or after brain scoring."
version: 0.3.0
---

# 2f-brain-validator

**Spec:** `phases/phase-2-brain-context-brd.md`

## Purpose
Final Phase 2 gate (per project). Coherence + faithfulness + lock. Each project brain is self-contained.

## 4 Stages

**A: Completeness** - all planned files present: About-Me (5) + Project (~13) + Config (profile-settings, cowork-instructions, language-preferences, project-instruction).

**B: Per-file scores** - every file >=9.5 (from 2e).

**C: Coherence** (7 pairs >=9.0):
1. positioning <-> offer
2. offer <-> icp
3. icp <-> gtm-motions
4. brand-voice <-> communication-style
5. brain <-> Phase 1 inputs (faithfulness, no drift)
6. goals-and-vision <-> project-instruction
7. MENA-fit + language consistency
Plus: no business bleed (this project's files contain only this project's business).

**D: Lock or loop** - all pass -> write _scoring/, update tracker + _progress, Telegram approval, suggest Phase 3. Any fail -> bridge-plan, gap-fill hints, re-run.

## Output
- `_scoring/phase-2-scores.md`, `coherence-map.md`, `bridge-plan.md`
- `tracker.md`, `_progress.md` updated
- INPUT-GAP report

## Threshold
Phase composite >=9.5. All coherence >=9.0. Zero business bleed. Zero unresolved hallucination.

## Anti-Patterns
1. Don't lock with any file <9.5
2. Don't lock with business bleed
3. Don't lock without Telegram approval
4. Don't ignore INPUT-GAPs

## Handoff
Phase 3 (smo-ai-gtm-strategy)
