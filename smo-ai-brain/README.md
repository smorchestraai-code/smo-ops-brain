# smo-ai-brain (Plugin)

Phase 2 of the SMO-AI customer journey. Converts a locked Phase 1 input folder into the customer's complete business brain at Class A.

**Version:** 0.3.0
**Consumes:** smo-ai-onboarding Phase 1 output (`0-Input/` + `references/`)
**Produces:** `1-ProjectBrain/` (About-Me + Project + Config) ready for the customer Claude cockpit

## What it does

Faithfully turns captured inputs into a structured business brain. Hard constraint: zero hallucination. Every brain claim cites its Phase 1 source. The brain represents what the customer actually said, never what Claude imagines.

Each project brain is **self-contained and project-level**. The founder presents differently per business (persona differs), so even About-Me diverges per project. No shared customer brain layer.

## Skills (6)

| Skill | Delivers |
|---|---|
| `2a-brain-orchestrator` | Read inputs, detect persona + complexity, plan file set, build source-map |
| `2b-about-me-builder` | About-Me (5 files, project-level, persona-framed) |
| `2c-project-builder` | Project business files (~13) + project-instruction.md |
| `2d-config-builder` | Exactly 3 config files (profile-settings, cowork-instructions, language-preferences) |
| `2e-brain-scorer` | 6-dim scoring incl. traceability (zero-hallucination gate) |
| `2f-brain-validator` | Coherence + faithfulness + Phase 2 lock |

## Commands

Standard quartet (every plugin): `brain-start`, `brain-guide`, `brain-status`, `brain-validate`.
Plugin-specific: `brain-build` (full chain), `brain-about-me` (2b), `brain-project` (2c), `brain-config` (2d).

Canonical entry: **`/brain-start`** — detects single vs multi project, organizes the workspace, verifies Phase 1 locked, then builds.

## Brain Structure

Project-level, self-contained: 5 About-Me + ~13 Project + 4 Config (3 from 2d + project-instruction from 2c).

Multi-business -> sibling projects under a customer master folder (organizational only, no shared brain). Single-business -> flat customer folder.

## Scoring

6-dim: Specificity, Evidence, Differentiation, Actionability, MENA-fit, **Traceability**. Composite >=9.5, traceability >=9.0, MENA-fit floor 8.0. Phase coherence: 7 pairs >=9.0 + no business bleed.

## Dogfood

Newmind-Coaching (Pro Services) + Newmind-Wellness (Ecom). Same founder Hosam Daghash, but each project gets its own persona-framed About-Me + Config. Tests project-level self-containment + business-bleed prevention + zero-hallucination.

Full spec: `phases/phase-2-brain-context-brd.md`.
