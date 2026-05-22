---
name: 2b-about-me-builder
description: "Generates founder-level About-Me brain files (personal background, professional experience, communication style, working preferences, goals and vision) from Phase 1 interview answers, memory extracts, and founder sources. Founder-level files are shared across sibling projects of the same founder. Every claim cites its Phase 1 source. Use when user runs /brain-about-me or as part of /brain-build."
version: 0.1.0
---

# 2b-about-me-builder

**Status:** v0.1
**Spec:** `phases/phase-2-brain-context-brd.md` Section 5

## Purpose
Generate 5 founder About-Me files. SHARED across sibling projects.

## Inputs
- `1-ProjectBrain/_source-map.md`
- `0-Input/interview-answers-extract.md`
- `0-Input/memory-extracts/` (operating-preferences, communication-style, network)
- `0-Input/sources/founder-linkedin.md`

## Files Generated
1. personal-background.md
2. professional-experience.md
3. communication-style.md
4. working-preferences.md
5. goals-and-vision.md

## Rules
- Every claim cites source per source-map
- INPUT-GAP fields get placeholder, not invention
- SHARED: write once, flag for sibling-project copy

## Self-score
6-dim incl. traceability >=9.0. Composite >=9.5. MENA-fit floor 8.0.

## Anti-Patterns
1. Don't invent founder facts
2. Don't let business-specific content in (that's 2c)
3. Don't drift across siblings

## Handoff
2e-brain-scorer
