---
name: 2d-config-builder
description: "Generates exactly 3 Claude Config brain files (profile-settings, cowork-instructions, language-preferences) that wire the project brain into the Claude cockpit. project-instruction is NOT produced here (it lives in the project-builder skill). Derives identity, role, voice, hard constraints, and language rules from the generated About-Me and Project files. Use when user runs /brain-config or as part of /brain-build."
version: 0.3.0
---

# 2d-config-builder

**Spec:** `phases/phase-2-brain-context-brd.md`

## Purpose
Generate EXACTLY 3 config files (project-level). project-instruction is delivered by 2c, not here.

## Inputs
- Generated About-Me/ + Project/ (from 2b, 2c)
- `0-Input/persona-and-priority.md` (language preference)
- `0-Input/tools-inventory.md` (MCP wiring hints)

## Files Generated (exactly 3)
1. profile-settings.md (Claude identity, role, default tone, hard constraints, approval surface)
2. cowork-instructions.md (CLAUDE.md: who the customer is for this business, core thesis, voice, hard nos, output standards)
3. language-preferences.md (per-channel language rules, dialect, code-switching)

## Rules
- Derive from generated brain (not raw inputs)
- Hard nos from goals-and-vision
- Voice from communication-style + brand-voice
- Project-level: write to THIS project's 1-ProjectBrain/Config/
- DO NOT produce project-instruction.md (that is 2c's job)

## Self-score
6-dim. Composite >=9.5. MENA-fit floor 8.0.

## Anti-Patterns
1. Don't contradict the brain files
2. Don't hardcode customer specifics in logic
3. Don't default language to English without checking persona-and-priority
4. Don't produce project-instruction (belongs to 2c)
5. Don't produce more than 3 files

## Handoff
2e-brain-scorer
