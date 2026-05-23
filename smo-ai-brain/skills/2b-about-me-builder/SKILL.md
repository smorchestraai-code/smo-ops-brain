---
name: 2b-about-me-builder
description: "Generates founder-level About-Me brain files (personal background, professional experience, communication style, working preferences, goals and vision) from Phase 1 interview answers, memory extracts, and founder sources. Founder-level files are shared across sibling projects of the same founder, hoisted to the customer master layer. Every claim cites its Phase 1 source. Use when user runs /brain-about-me or as part of /brain-build."
version: 0.2.0
---

# 2b-about-me-builder

**Spec:** `phases/phase-2-brain-context-brd.md`

## Purpose
Generate 5 founder About-Me files. SHARED across sibling projects (same founder).

## Inputs
- `1-ProjectBrain/_source-map.md`
- `0-Input/interview-answers-extract.md`
- `0-Input/memory-extracts/` (operating-preferences, communication-style, network)
- `0-Input/sources/founder-linkedin.md`

## Files Generated
personal-background, professional-experience, communication-style, working-preferences, goals-and-vision.

## Rules
- Every claim cites source per source-map
- INPUT-GAP fields get placeholder, not invention

## Multi-Project Master Mode
About-Me = FOUNDER-level = META. In multi-project mode, write ONCE to `<Customer>/_customer/About-Me/`, not into each project. On the second project's run, verify no drift (founder facts identical), do not duplicate. Single-project: write to the project's own 1-ProjectBrain/About-Me/.

## Self-score
6-dim incl. traceability >=9.0. Composite >=9.5. MENA-fit floor 8.0.

## Anti-Patterns
1. Don't invent founder facts
2. Don't let business-specific content in (that's 2c)
3. Don't drift across siblings

## Handoff
2e-brain-scorer
