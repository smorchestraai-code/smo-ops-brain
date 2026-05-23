---
name: 2a-brain-orchestrator
description: "Reads a locked Phase 1 input folder, detects persona and business complexity, plans the brain file set (core plus adaptive extensions), and builds the source-map that maps every brain field to its Phase 1 source. First skill in Phase 2. Use when user runs /brain-build or after Phase 1 input capture locks. Enforces zero-hallucination by requiring every downstream claim to cite a source."
version: 0.2.0
---

# 2a-brain-orchestrator (Phase 2 entry)

**Spec:** `phases/phase-2-brain-context-brd.md`

## Purpose
Read all Phase 1 inputs, plan the brain, build the anti-hallucination source-map.

## Preconditions
Phase 1 locked. If `_progress.md` does not show Phase 1 locked: exit with instructions.

## Process
1. Read `0-Input/` + `references/`
2. Detect persona from persona-and-priority.md
3. Detect complexity signals
4. Plan brain file set: CORE (5 About-Me + ~8 Project + 4 Config) + EXTENDED per complexity
5. Build `_source-map.md`: per brain field, feeding Phase 1 source(s). No source -> INPUT-GAP.
6. Detect sibling projects (multi-project): note which About-Me + meta-config are SHARED.

## Output
- `1-ProjectBrain/_build-plan.md`
- `1-ProjectBrain/_source-map.md`

## Multi-Project Master Mode
If customer has sibling projects, detect master mode and plan altitude per artifact:
- About-Me + meta-Config (profile-settings, cowork-instructions, language-preferences) -> CUSTOMER level (`<Customer>/_customer/`), written once
- Project files + project-instruction -> PROJECT level
See `references/multi-project-master-mode.md`. Single-project: everything in the project's own 1-ProjectBrain/.

## Self-score
6-dim incl. traceability. Source-map covers every planned field. Composite >=9.5.

## Anti-Patterns
1. Don't plan a field with no input source (INPUT-GAP)
2. Don't cram multi-business into one brain
3. Don't hardcode customer specifics

## Handoff
2b, 2c, 2d
