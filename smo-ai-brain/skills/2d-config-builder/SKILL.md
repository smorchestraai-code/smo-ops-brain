---
name: 2d-config-builder
description: "Generates Claude Config brain files (profile settings, cowork instructions, project instruction, language preferences) that wire the business brain into the customer Claude cockpit. Derives identity, role, voice, hard constraints, and language rules from the generated About-Me and Project files. Use when user runs /brain-config or as part of /brain-build."
version: 0.1.0
---

# 2d-config-builder

**Status:** v0.1
**Spec:** `phases/phase-2-brain-context-brd.md` Section 5

## Purpose
Generate the 4 Config files that make Claude operate as the customer's coworker.

## Inputs
- Generated About-Me/ + Project/ (from 2b, 2c)
- `0-Input/persona-and-priority.md`
- `0-Input/tools-inventory.md`

## Files Generated
1. profile-settings.md
2. cowork-instructions.md (CLAUDE.md)
3. project-instruction.md
4. language-preferences.md

## Rules
- Derive from generated brain (not raw inputs)
- Hard nos from goals-and-vision
- Voice from communication-style + brand-voice

## Self-score
6-dim. Composite >=9.5. MENA-fit floor 8.0.

## Anti-Patterns
1. Don't contradict the brain files
2. Don't hardcode customer specifics in logic
3. Don't default language to English without checking persona-and-priority

## Handoff
2e-brain-scorer
