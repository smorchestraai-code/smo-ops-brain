---
name: 2e-brain-scorer
description: "Scores each generated brain file on a 6-dimension rubric (specificity, evidence, differentiation, actionability, MENA-fit, traceability). Traceability verifies every non-trivial claim cites a resolvable Phase 1 source - the zero-hallucination gate. Flags unsourced claims and INPUT-GAPs. Use after brain files are generated, as part of /brain-build."
version: 0.1.0
---

# 2e-brain-scorer

**Status:** v0.1
**Spec:** `phases/phase-2-brain-context-brd.md` Section 6

## Purpose
Score every brain file. Enforce traceability (zero hallucination).

## 6-Dim Rubric
1. Specificity
2. Evidence
3. Differentiation
4. Actionability
5. MENA-fit (floor 8.0)
6. **Traceability** (every claim cites resolvable Phase 1 source; floor 9.0)

## Traceability Check
For each non-trivial claim:
- Resolve cited source against `_source-map.md` + actual Phase 1 files
- Missing/unresolvable -> penalty
- INPUT-GAP placeholders OK; unsourced INVENTED claims NOT

## Output
Per-file 6-dim score block written into each brain file. `_scoring/phase-2-file-scores.md` aggregate.

## Threshold
Composite >=9.5, every dim >=8.0, traceability >=9.0, MENA-fit >=8.0.

## Handoff
2f-brain-validator
