---
name: 3a2-asset-list-planner
description: "Derives the adaptive asset count and asset list for this customer based on persona + complexity signals from the brain. No hardcoded counts. Outputs the planned asset list into _build-plan.md with per-asset justification. Use when user runs /gtm-plan or as part of /gtm-build chain after 3a1-playbook-selector."
version: 0.1.0
---

# 3a2-asset-list-planner

## Purpose
Decide how many of what for THIS customer. Adaptive, not template.

## Persona Base
SaaS / Pro Services / Enterprise / Ecom each have base asset patterns.

## Complexity Modifiers
- Multi-product: +1-2 product-education sequences
- Multi-pipeline: +1 re-engagement variant
- Heavy WhatsApp culture: +2 WhatsApp templates
- Bilingual: +1 variant per primary asset
- Content-heavy founder: +YouTube outlines + LinkedIn batch

## Process
1. Start with persona base.
2. Apply complexity modifiers.
3. Apply playbook overrides.
4. Apply customer priority (from Phase 1).
5. Write planned list with per-asset justification.

## Output
- Updated `_build-plan.md` with adaptive list

## Self-score
6-dim. Every count must have brain-signal justification.

## Anti-Patterns
1. Don't use template counts (8 sequences, 5 funnels = Sam-specific, banned)
2. Don't over-spec
3. Don't under-spec

## Handoff
3b, 3c, 3d, 3e generators
