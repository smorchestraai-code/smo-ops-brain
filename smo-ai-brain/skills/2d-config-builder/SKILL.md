---
name: 2d-config-builder
description: "Generates Claude Config brain files (profile settings, cowork instructions, project instruction, language preferences) that wire the business brain into the customer Claude cockpit. Config splits by altitude: profile-settings, cowork-instructions, language-preferences are customer-level meta (hoisted to the master layer); project-instruction is project-level. Use when user runs /brain-config or as part of /brain-build."
version: 0.2.0
---

# 2d-config-builder

**Spec:** `phases/phase-2-brain-context-brd.md`

## Purpose
Generate the 4 Config files that make Claude operate as the customer's coworker.

## Inputs
- Generated About-Me/ + Project/ (from 2b, 2c)
- `0-Input/persona-and-priority.md`
- `0-Input/tools-inventory.md`

## Files Generated
1. profile-settings.md (META)
2. cowork-instructions.md (META, global CLAUDE.md)
3. language-preferences.md (META)
4. project-instruction.md (PROJECT)

## Multi-Project Master Mode (CRITICAL - config splits by altitude)
Config is NOT uniform:
- META (customer-level, written once to `<Customer>/_customer/Config/`): profile-settings, cowork-instructions, language-preferences. Describe the FOUNDER + global cockpit identity. Same across all the founder's projects.
- PROJECT-level (per project, `<project>/1-ProjectBrain/Config/`): project-instruction. This project's priorities, active wedge, ICP, plugin routing.

Multi-project: write 3 meta files once to `_customer/Config/`; project-instruction per project. Second project's run: meta-config exists, verify no drift, don't duplicate. Single-project: all 4 in the project's own Config/.

This is the Cowork pattern: global CLAUDE.md (cowork-instructions) + project CLAUDE.md (project-instruction).

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
4. Don't write meta-config per-project in multi-project mode (hoist to master)

## Handoff
2e-brain-scorer
