---
name: 2b-about-me-builder
description: "Generates project-level founder About-Me brain files (personal background, professional experience, communication style, working preferences, goals and vision) from Phase 1 interview answers, memory extracts, and founder sources. About-Me is project-level: even for the same founder, the persona differs per business, so each project gets its own About-Me. Every claim cites its Phase 1 source. Use when user runs /brain-about-me or as part of /brain-build."
version: 0.3.0
---

# 2b-about-me-builder

**Spec:** `phases/phase-2-brain-context-brd.md`

## Purpose
Generate 5 founder About-Me files for THIS project. Project-level: the founder's persona differs per business, so coaching About-Me != wellness About-Me even though it is the same person.

## Inputs
- `1-ProjectBrain/_source-map.md` (from 2a)
- `0-Input/interview-answers-extract.md`
- `0-Input/memory-extracts/` (operating-preferences, communication-style, network)
- `0-Input/sources/` (founder profile relevant to THIS business)

## Files Generated (project-level)
1. personal-background.md (origin story relevant to this business persona)
2. professional-experience.md (credentials/track record framed for this business)
3. communication-style.md (voice for this business context)
4. working-preferences.md (routine, decision style, energy, tools)
5. goals-and-vision.md (goals for this business)

## Rules
- Project-level: write to THIS project's `1-ProjectBrain/About-Me/`
- Persona framed for this specific business (coaching vs wellness)
- Every claim cites source per source-map
- INPUT-GAP fields get placeholder, not invention

## Self-score
6-dim incl. traceability >=9.0. Composite >=9.5. MENA-fit floor 8.0.

## Anti-Patterns
1. Don't invent founder facts (cite or INPUT-GAP)
2. Don't write a generic founder profile (frame for this business persona)
3. Don't put business-specific offer/ICP content here (that's 2c)

## Handoff
2e-brain-scorer
