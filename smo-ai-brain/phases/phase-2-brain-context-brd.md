# Phase 2 BRD: Brain Context

**Plugin:** smo-ai-brain
**Phase:** 2 (Brain Context)
**Status:** v0.4 (altitude model: 3 config files at customer master, everything else project-level)
**Date:** 2026-05-23
**Composite target:** 10/10

---

## 1. Phase Vision

Convert a locked Phase 1 input folder into the customer's complete business brain at Class A. Loads into the Claude cockpit, makes Claude the customer's trained coworker. Hard constraint: ZERO hallucination. Every brain claim traces to a Phase 1 input.

## 2. Phase Outcome

Each project's `1-ProjectBrain/` at Class A. Everything project-level except the 3 config files.

### About-Me (5, project-framed) - PROJECT
personal-background, professional-experience, communication-style, working-preferences, goals-and-vision.

### Project (~13) - PROJECT
business-overview, positioning, brand-voice, icp (single), offer, products-catalog, pricing-strategy, competitors, gtm-motions, content-guidelines, faq-objections, testimonials, pipeline-definitions.

### Config (4)
- 3 from 2d: profile-settings, cowork-instructions, language-preferences -> CUSTOMER MASTER (multi-business) / project (single). Founder's ONE global cockpit identity.
- 1 from 2c: project-instruction -> PROJECT

## 2b. Altitude Model

Everything is PROJECT-level EXCEPT the 3 config files.

```
<Customer>/                       (master)
  _customer/Config/               (profile-settings, cowork-instructions, language-preferences) <- CUSTOMER MASTER
  <Customer>-<Project1>/1-ProjectBrain/
    About-Me/ (5)                 <- PROJECT (persona-framed per business)
    Project/ (~13)                <- PROJECT
    Config/project-instruction.md <- PROJECT
  <Customer>-<Project2>/1-ProjectBrain/ ...
```

The 3 config files = founder's ONE global cockpit identity (shared across businesses). Single-project: all 4 config files in the project. Phase 1 onboarding NOT impacted (per-project). brain-start organizes.

## 3. Skill Chain

```
/brain-start (detect single/multi, organize by altitude, verify Phase 1 locked)
  -> /brain-build:
     2a-brain-orchestrator (read, plan, source-map)
     2b-about-me-builder (5 About-Me, project-level, persona-framed)
     2c-project-builder (Project files + project-instruction.md)
     2d-config-builder (3 config files; customer-master for multi-business)
     2e-brain-scorer (6-dim incl traceability)
     2f-brain-validator (coherence + faithfulness + lock)
```

Source Map (2a): every brain field maps to Phase 1 source. No source -> INPUT-GAP, never invent.

## 4. Skill Ownership

| Skill | Delivers | Altitude |
|---|---|---|
| 2a | _build-plan.md, _source-map.md | - |
| 2b | About-Me/ (5) | PROJECT |
| 2c | Project/ (~13) + Config/project-instruction.md | PROJECT |
| 2d | profile-settings, cowork-instructions, language-preferences | CUSTOMER MASTER (multi) / project (single) |
| 2e | per-file 6-dim scores | - |
| 2f | coherence, lock, _scoring/ | - |

## 5. Commands

Standard quartet (every plugin): brain-start, brain-guide, brain-status, brain-validate.
Plugin-specific: brain-build, brain-about-me (2b), brain-project (2c), brain-config (2d).
Canonical entry: brain-start.

## 6. Scoring

Micro: 6-dim (Specificity, Evidence, Differentiation, Actionability, MENA-fit, Traceability). Composite >=9.5, traceability >=9.0, MENA-fit floor 8.0.
Macro: 7 coherence pairs >=9.0 + no business bleed + 3 config files at master with no drift (multi-project). Phase composite >=9.5.

## 7. Test Plan (dogfood)

Newmind master: Newmind-Coaching (Pro Services) + Newmind-Wellness (Ecom). Per-project About-Me + Project + project-instruction (diverge). Customer-master: 3 config files at `Newmind/_customer/Config/` (shared, no drift). Cross-project: no business bleed.

## 8. Definition of Done

6 skills built. Both Newmind projects Class A. Traceability >=9.0 every file. project-instruction by 2c. 2d delivers exactly 3 config files at customer master. No business bleed. No config drift. brain-start organizes by altitude. Telegram approval tested.

## 9. Anti-Patterns (BANNED)

1. Never invent without a Phase 1 source (INPUT-GAP instead)
2. Never hardcode for a customer
3. Never let business bleed across siblings
4. Never ship a brain file <9.5
5. Never skip traceability
6. Never drift from what the customer said
7. Never lock without Telegram approval
8. Never strip Arabic / break RTL
9. Never put the 3 config files per-project in multi-business mode (hoist to master)
10. Never have 2d produce project-instruction (that is 2c)

## 10. Architect Decisions (Locked)

1. Multi-business via sibling projects, not multi-ICP brains
2. **About-Me + Project + project-instruction are PROJECT-level** (founder persona differs per business)
3. **The 3 config files (profile-settings, cowork-instructions, language-preferences) are CUSTOMER MASTER** for multi-business - the founder's ONE global cockpit identity. The only macro/customer-level brain artifacts.
4. **2d delivers exactly 3 config files**; project-instruction moves to 2c
5. Traceability = 6th scoring dim (>=9.0)
6. Source-map mandatory (2a)
7. **Command quartet standard**: every plugin ships start/guide/status/validate
8. brain-start canonical: detects single/multi, organizes by altitude, verifies Phase 1, builds
9. Dogfood = Newmind-Coaching + Newmind-Wellness under Newmind master

## 11. Versioning

- v0.1: BRD + 6 skills
- v0.2: multi-project master mode (About-Me + config shared) - SUPERSEDED
- v0.3: all project-level - SUPERSEDED
- v0.4 (current): altitude model - 3 config files at customer master, everything else project-level
- v1.0: both Newmind projects pass, Phase 2 locked
