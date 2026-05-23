---
name: 2f-brain-validator
description: "Validates per-project brain coherence and faithfulness to Phase 1 inputs, then locks Phase 2 or triggers gap-fill loop. Per project: About-Me, Project, and project-instruction. The 3 config files (profile-settings, cowork-instructions, language-preferences) are customer-master for multi-business customers. Checks brain-internal coherence (positioning agrees with offer agrees with ICP), brain-to-input faithfulness (no drift), and no business bleed across sibling projects. Requires Telegram operator approval before lock. Use when user runs /brain-validate or after brain scoring."
version: 0.4.0
---

# 2f-brain-validator

**Spec:** `phases/phase-2-brain-context-brd.md`

## Purpose
Final Phase 2 gate (per project). Coherence + faithfulness + lock.

## 4 Stages

**A: Completeness + Altitude** - per project: About-Me (5) + Project (~13) + project-instruction present. The 3 config files (profile-settings, cowork-instructions, language-preferences) present at CUSTOMER MASTER (`_customer/Config/`) for multi-project, or in the project's Config/ for single-project.

**B: Per-file scores** - every file >=9.5 (from 2e).

**C: Coherence** (7 pairs >=9.0):
1. positioning <-> offer
2. offer <-> icp
3. icp <-> gtm-motions
4. brand-voice <-> communication-style
5. brain <-> Phase 1 inputs (faithfulness, no drift)
6. goals-and-vision <-> project-instruction
7. MENA-fit + language consistency
Plus: no business bleed. Multi-project: the 3 config files exist once at customer master with no drift; About-Me/Project/project-instruction are project-level and diverge correctly.

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
