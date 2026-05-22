# smo-ai-brain (Plugin)

Phase 2 of the SMO-AI customer journey. Converts a locked Phase 1 input folder into the customer's complete business brain at Class A.

**Version:** 0.1.0
**Consumes:** smo-ai-onboarding Phase 1 output (`0-Input/` + `references/`)
**Produces:** `1-ProjectBrain/` (About-Me + Project + Config) ready for the customer Claude cockpit

## What it does

Faithfully turns captured inputs into a structured business brain. Hard constraint: zero hallucination. Every brain claim cites its Phase 1 source. The brain represents what the customer actually said, never what Claude imagines.

## Skills (6)

| Skill | Job |
|---|---|
| `2a-brain-orchestrator` | Read inputs, detect persona + complexity, plan file set, build source-map |
| `2b-about-me-builder` | Founder files (shared across sibling projects) |
| `2c-project-builder` | Business files (per-project, no bleed) |
| `2d-config-builder` | Claude config (profile, cowork-instructions, project-instruction, language) |
| `2e-brain-scorer` | 6-dim scoring incl. traceability (zero-hallucination gate) |
| `2f-brain-validator` | Coherence + faithfulness + Phase 2 lock |

## Commands

| Command | Purpose |
|---|---|
| `/brain-build <customer>` | Canonical entry. Full Phase 2 chain. |
| `/brain-guide [<customer>]` | Copilot, recommends next |
| `/brain-status [<customer>]` | Dashboard with per-file scores |
| `/brain-about-me <customer>` | Manual 2b |
| `/brain-project <customer>` | Manual 2c |
| `/brain-config <customer>` | Manual 2d |
| `/brain-validate <customer>` | Manual 2f, lock |

## Brain Structure (adaptive)

CORE always: 5 About-Me + ~13 Project + 4 Config.
Multi-business handled via SIBLING PROJECTS, not multi-ICP brains. About-Me shared across siblings, Project diverges.

## Scoring

6-dim rubric: Specificity, Evidence, Differentiation, Actionability, MENA-fit, **Traceability**. Composite >=9.5, traceability >=9.0, MENA-fit floor 8.0. Phase coherence: 7 pairs >=9.0 + no business bleed + no About-Me drift.

## Dogfood

Newmind-Coaching (Pro Services) + Newmind-Wellness (Ecom). Same founder Hosam Daghash, shared About-Me, divergent Project brains. Tests multi-project handling + business-bleed prevention + zero-hallucination.

Full spec: `phases/phase-2-brain-context-brd.md`.
