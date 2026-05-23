# smo-ai-brain (Plugin)

Phase 2 of the SMO-AI customer journey. Converts a locked Phase 1 input folder into the customer's complete business brain at Class A.

**Version:** 0.4.0
**Consumes:** smo-ai-onboarding Phase 1 output (`0-Input/` + `references/`)
**Produces:** `1-ProjectBrain/` (About-Me + Project + Config) ready for the customer Claude cockpit

## What it does

Faithfully turns captured inputs into a structured business brain. Hard constraint: zero hallucination. Every brain claim cites its Phase 1 source.

Everything is **project-level** (About-Me, Project, project-instruction) EXCEPT the 3 config files (profile-settings, cowork-instructions, language-preferences), which are the founder's ONE global cockpit identity, hoisted to the **customer master** for multi-business customers. The founder presents differently per business, so persona/business content diverges per project; the cockpit identity is shared.

## Skills (6)

| Skill | Delivers |
|---|---|
| `2a-brain-orchestrator` | Read inputs, detect persona + complexity, plan file set, build source-map |
| `2b-about-me-builder` | About-Me (5 files, project-level, persona-framed) |
| `2c-project-builder` | Project business files (~13) + project-instruction.md |
| `2d-config-builder` | The 3 config files (customer-master for multi-business) |
| `2e-brain-scorer` | 6-dim scoring incl. traceability (zero-hallucination gate) |
| `2f-brain-validator` | Coherence + faithfulness + Phase 2 lock |

## Commands

Standard quartet (every plugin): `brain-start`, `brain-guide`, `brain-status`, `brain-validate`.
Plugin-specific: `brain-build` (full chain), `brain-about-me` (2b), `brain-project` (2c), `brain-config` (2d).

Canonical entry: **`/brain-start`** — detects single vs multi project, organizes the workspace by altitude, verifies Phase 1 locked, then builds.

## Altitude

Project-level: About-Me (5) + Project (~13) + project-instruction.
Customer-master (multi-business only): profile-settings, cowork-instructions, language-preferences (founder's ONE global cockpit identity).
Single-business: flat customer folder, all config in the project.

## Scoring

6-dim: Specificity, Evidence, Differentiation, Actionability, MENA-fit, **Traceability**. Composite >=9.5, traceability >=9.0, MENA-fit floor 8.0. Phase coherence: 7 pairs >=9.0 + no business bleed.

## Dogfood

Newmind-Coaching (Pro Services) + Newmind-Wellness (Ecom). Same founder Hosam Daghash. Per-project: persona-framed About-Me + Project + project-instruction. Customer-master: the 3 config files at `Newmind/_customer/Config/`.

Full spec: `phases/phase-2-brain-context-brd.md`.
