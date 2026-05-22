---
name: 2c-project-builder
description: "Generates business-level Project brain files (business overview, positioning, brand voice, ICP, offer, products catalog, pricing, competitors, GTM motions, content guidelines, FAQ objections, testimonials, pipeline definitions) for a single project. Single ICP per project; multi-business is handled by sibling projects, not multiple ICPs in one brain. Every claim cites its Phase 1 source. Use when user runs /brain-project or as part of /brain-build."
version: 0.1.0
---

# 2c-project-builder

**Status:** v0.1
**Spec:** `phases/phase-2-brain-context-brd.md` Section 5

## Purpose
Generate business-level Project files for THIS project (single business).

## Inputs
- `1-ProjectBrain/_source-map.md`
- `0-Input/sources/` (THIS business's pages)
- `0-Input/memory-extracts/` (offer, customer-conversations, sales-history)
- `0-Input/interview-answers-extract.md`
- `references/docs/`, `references/`

## Files Generated (core ~13)
business-overview, positioning, brand-voice, icp, offer, products-catalog, pricing-strategy, competitors, gtm-motions, content-guidelines, faq-objections, testimonials, pipeline-definitions.

## Project Scope Discipline
Read persona-and-priority.md Business Scope + Out of Scope. Include ONLY this project's business. Coaching project = coaching only. Wellness project = wellness only. No bleed.

## Rules
- Single ICP
- Every claim cites source
- INPUT-GAP placeholders, no invention
- Respect Out of Scope

## Self-score
6-dim incl. traceability >=9.0. Composite >=9.5. MENA-fit floor 8.0.

## Anti-Patterns
1. Don't include sibling-project content (no bleed)
2. Don't create multiple ICPs
3. Don't invent

## Handoff
2e-brain-scorer
