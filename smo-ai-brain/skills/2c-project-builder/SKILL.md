---
name: 2c-project-builder
description: "Generates business-level Project brain files (business overview, positioning, brand voice, ICP, offer, products catalog, pricing, competitors, GTM motions, content guidelines, FAQ objections, testimonials, pipeline definitions) PLUS the project-instruction config file for a single project. Single ICP per project; multi-business handled by sibling projects. Every claim cites its Phase 1 source. Use when user runs /brain-project or as part of /brain-build."
version: 0.3.0
---

# 2c-project-builder

**Spec:** `phases/phase-2-brain-context-brd.md`

## Purpose
Generate business-level Project files for THIS project (single business) PLUS project-instruction.md (project-level config, moved here from 2d).

## Inputs
- `1-ProjectBrain/_source-map.md`
- `0-Input/sources/` (THIS business's pages)
- `0-Input/memory-extracts/` (offer, customer-conversations, sales-history)
- `0-Input/interview-answers-extract.md`
- `references/docs/`, `references/`

## Files Generated
Project/ business files (core ~13): business-overview, positioning, brand-voice, icp, offer, products-catalog, pricing-strategy, competitors, gtm-motions, content-guidelines, faq-objections, testimonials, pipeline-definitions.
PLUS Config/project-instruction.md (this project's priorities, active wedge, ICP, plugin routing).

## Project Scope Discipline
Read persona-and-priority.md Business Scope + Out of Scope. Include ONLY this project's business. No bleed.

## Rules
- Single ICP per project
- project-instruction.md derived from this project's brain + priority
- Every claim cites source; INPUT-GAP placeholders, no invention

## Self-score
6-dim incl. traceability >=9.0. Composite >=9.5. MENA-fit floor 8.0.

## Anti-Patterns
1. Don't include sibling-project business content (no bleed)
2. Don't create multiple ICPs
3. Don't invent
4. Don't omit project-instruction.md

## Handoff
2e-brain-scorer
