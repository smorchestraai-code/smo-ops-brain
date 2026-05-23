---
name: 2d-config-builder
description: "Generates the 3 customer-level Claude Config files (profile-settings, cowork-instructions, language-preferences) - the founder's single global cockpit identity, shared across all their businesses. In multi-project customers these are written ONCE to the customer master; in single-project they live in the project. project-instruction is NOT produced here (it lives in the project-builder skill, project-level). Use when user runs /brain-config or as part of /brain-build."
version: 0.4.0
---

# 2d-config-builder

**Spec:** `phases/phase-2-brain-context-brd.md`

## Purpose
Generate EXACTLY 3 config files = the founder's ONE global cockpit identity. These are the ONLY customer-level (macro) brain artifacts. Everything else is project-level.

## Inputs
- Generated About-Me/ + Project/ (from 2b, 2c, for voice/identity derivation)
- `0-Input/persona-and-priority.md` (language preference)
- `0-Input/tools-inventory.md` (MCP wiring hints)

## Files Generated (exactly 3)
1. profile-settings.md (Claude identity, role, default tone, hard constraints, approval surface)
2. cowork-instructions.md (global CLAUDE.md: founder identity, core thesis, voice, hard nos, output standards)
3. language-preferences.md (per-channel language rules, dialect, code-switching)

## Altitude (CRITICAL)
- **Multi-project customer:** write the 3 files ONCE to `<Customer>/_customer/Config/`. On a sibling project's run, they already exist: verify no drift, do not duplicate.
- **Single-project customer:** write the 3 files to the project's own `1-ProjectBrain/Config/`.

These 3 files are the founder's global cockpit identity (ONE Claude across all businesses). They do NOT diverge per business.

## Rules
- Derive from generated brain (founder-level facts, not business-specific)
- Hard nos from goals-and-vision
- DO NOT produce project-instruction.md (that is 2c, project-level)
- Exactly 3 files, nothing more

## Self-score
6-dim. Composite >=9.5. MENA-fit floor 8.0.

## Anti-Patterns
1. Don't write the 3 config files per-project in multi-project mode (hoist to customer master)
2. Don't produce project-instruction (belongs to 2c)
3. Don't produce more than 3 files
4. Don't make these business-specific (they are founder-global)

## Handoff
2e-brain-scorer
