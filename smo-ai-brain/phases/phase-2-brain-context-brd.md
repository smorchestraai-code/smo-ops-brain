# Phase 2 BRD: Brain Context

**Plugin:** smo-ai-brain
**Phase:** 2 (Brain Context)
**Status:** v0.3 (self-contained project-level model + command quartet)
**Date:** 2026-05-23
**Composite target:** 10/10

---

## 1. Phase Vision

Convert a locked Phase 1 input folder into the customer's complete business brain at Class A. Loads into the Claude cockpit, makes Claude the customer's trained coworker. Hard constraint: ZERO hallucination. Every brain claim traces to a Phase 1 input.

## 2. Phase Outcome (self-contained, project-level)

Each project's `1-ProjectBrain/` at Class A. Everything is project-level: the founder presents differently per business, so even About-Me diverges per project.

### About-Me (5, project-framed)
personal-background, professional-experience, communication-style, working-preferences, goals-and-vision.

### Project (~13)
business-overview, positioning, brand-voice, icp (single), offer, products-catalog, pricing-strategy, competitors, gtm-motions, content-guidelines, faq-objections, testimonials, pipeline-definitions.

### Config (4)
- 3 from 2d: profile-settings, cowork-instructions, language-preferences
- 1 from 2c: project-instruction

Adaptive: CORE always + EXTENDED by complexity. Multi-BUSINESS handled via sibling projects, not multi-ICP brains.

## 2b. Project Structure (organizational)

Single project: customer folder = project folder (flat).
Multi project: master folder (customer name, organizational only) + project subfolders. NO shared brain layer. Each project brain fully self-contained and portable.

```
<Customer>/
  _customer/_customer-INDEX.md    (project roster, no brain)
  <Customer>-<Project1>/1-ProjectBrain/  (About-Me + Project + Config, self-contained)
  <Customer>-<Project2>/1-ProjectBrain/  (independent)
```

Phase 1 onboarding NOT impacted (runs per project). brain-start organizes folders.

## 3. Skill Chain

```
/brain-start (detect single/multi, organize workspace, verify Phase 1 locked)
  -> /brain-build:
     2a-brain-orchestrator (read, plan, source-map)
     2b-about-me-builder (5 About-Me, project-level, persona-framed)
     2c-project-builder (Project files + project-instruction.md)
     2d-config-builder (exactly 3: profile-settings, cowork-instructions, language-preferences)
     2e-brain-scorer (6-dim incl traceability)
     2f-brain-validator (coherence + faithfulness + lock)
```

Source Map (2a): every brain field maps to Phase 1 source. No source -> INPUT-GAP, never invent.

## 4. Skill Ownership (revamped)

| Skill | Delivers |
|---|---|
| 2a | _build-plan.md, _source-map.md |
| 2b | About-Me/ (5, project-level) |
| 2c | Project/ (~13) + Config/project-instruction.md |
| 2d | Config/ (exactly 3: profile-settings, cowork-instructions, language-preferences) |
| 2e | per-file 6-dim scores |
| 2f | coherence, lock, _scoring/ |

## 5. Commands (quartet + specific)

Standard quartet (every plugin): brain-start, brain-guide, brain-status, brain-validate.
Plugin-specific: brain-build (full chain), brain-about-me (2b), brain-project (2c), brain-config (2d).
Canonical entry: brain-start (organizes workspace, then builds).

## 6. Scoring

Micro: 6-dim (Specificity, Evidence, Differentiation, Actionability, MENA-fit, Traceability). Composite >=9.5, traceability >=9.0, MENA-fit floor 8.0.
Macro: 7 coherence pairs >=9.0 (positioning<->offer, offer<->icp, icp<->gtm, brand-voice<->communication-style, brain<->Phase 1 faithfulness, goals<->project-instruction, MENA+language) + no business bleed. Phase composite >=9.5.

## 7. Test Plan (dogfood)

Newmind master with Newmind-Coaching (Pro Services) + Newmind-Wellness (Ecom). Each self-contained: own About-Me (persona-framed per business) + Project + Config. Cross-project: no business bleed. Per project: traceability >=9.0, coherence >=9.0.

## 8. Definition of Done

6 skills built. Both Newmind projects Class A, self-contained. Traceability >=9.0 every file. project-instruction delivered by 2c. Config skill delivers exactly 3 files. No business bleed. Zero customer-specific code. brain-start organizes single/multi correctly. Telegram approval tested.

## 9. Anti-Patterns (BANNED)

1. Never invent without a Phase 1 source (INPUT-GAP instead)
2. Never hardcode for a customer
3. Never let business bleed across siblings
4. Never ship a brain file <9.5
5. Never skip traceability
6. Never drift from what the customer said
7. Never lock without Telegram approval
8. Never strip Arabic / break RTL
9. Never share/hoist brain across projects (each self-contained)
10. Never have 2d produce project-instruction (that is 2c)

## 10. Architect Decisions (Locked)

1. Multi-business via sibling projects, not multi-ICP brains
2. **About-Me is PROJECT-level** (founder persona differs per business) - reversed from v0.2 master-hoisting
3. **No shared customer brain layer** - each project self-contained and portable
4. **2d delivers exactly 3 config files**; project-instruction moves to 2c
5. Traceability = 6th scoring dim (>=9.0), zero-hallucination core differentiator
6. Source-map mandatory (2a)
7. **Command quartet standard**: every plugin ships start/guide/status/validate
8. brain-start canonical: detects single/multi, organizes workspace, verifies Phase 1, builds
9. Dogfood = Newmind-Coaching + Newmind-Wellness under Newmind master

## 11. Versioning

- v0.1: BRD + 6 skills
- v0.2: multi-project master mode (shared layer) - SUPERSEDED
- v0.3 (current): self-contained project-level model, About-Me project-level, config skill 3 files, project-instruction in 2c, command quartet + brain-start
- v1.0: both Newmind projects pass, Phase 2 locked
