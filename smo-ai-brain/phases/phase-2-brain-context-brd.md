# Phase 2 BRD: Brain Context

**Plugin:** smo-ai-brain
**Phase:** 2 (Brain Context)
**Status:** v0.2 (BRD locked + multi-project master mode added)
**Date:** 2026-05-23
**Composite target:** 10/10

---

## 1. Phase Vision

Convert a locked Phase 1 input folder into the customer's complete business brain at Class A. Loads into the customer Claude cockpit, makes Claude their trained coworker. Hard constraint: ZERO hallucination. Every brain claim traces to a Phase 1 input.

## 2. Phase Outcome

A populated `1-ProjectBrain/` at Class A.

### About-Me (founder-level, SHARED)
personal-background, professional-experience, communication-style, working-preferences, goals-and-vision.

### Project (business-level, PER-PROJECT)
business-overview, positioning, brand-voice, icp, offer, products-catalog, pricing-strategy, competitors, gtm-motions, content-guidelines, faq-objections, testimonials, pipeline-definitions.

### Config
profile-settings, cowork-instructions, project-instruction, language-preferences.

### Adaptive Rule
CORE always (5 About-Me + ~8 Project + 4 Config). EXTENDED by complexity. Multi-BUSINESS handled via sibling projects, not multi-ICP brains.

## 2b. Multi-Project Master Structure

Multiple sibling projects split by ALTITUDE into customer-master + per-project.

```
<Customer>/
  _customer/                    (META - written once)
    About-Me/                   (5 founder files)
    Config/                     (profile-settings, cowork-instructions, language-preferences)
  <Customer>-<Project1>/
    1-ProjectBrain/
      Project/                  (business files)
      Config/project-instruction.md
  <Customer>-<Project2>/ ...
```

Altitude rule: About-Me (2b) + 3 meta-config files (2d) = CUSTOMER level, once. Project files (2c) + project-instruction (2d) = PROJECT level.

Cowork loading model: global CLAUDE.md (cowork-instructions, customer-level, always loaded) + project CLAUDE.md (project-instruction, loaded in project folder). One founder, one cockpit identity, multiple project contexts.

Single-project: no `_customer/` layer. Phase 1 onboarding NOT impacted (runs per-project); meta-hoisting is purely Phase 2.

## 3. Scope

In: read locked Phase 1, generate About-Me/Project/Config, traceability enforcement, multi-project altitude split, bilingual EN/AR, coherence + lock.
Out: Phase 1 capture, Phase 3 GTM, customer hardcoding.

## 4. Architecture

```
/brain-build
  -> 2a-brain-orchestrator (read, detect persona+complexity+multi-project, plan, source-map)
  -> 2b-about-me-builder (founder; hoist to _customer in multi-project)
  -> 2c-project-builder (business; per-project)
  -> 2d-config-builder (meta-config -> _customer; project-instruction -> project)
  -> 2e-brain-scorer (6-dim incl traceability)
  -> 2f-brain-validator (coherence + faithfulness + master assembly, lock)
```

Source Map: 2a maps every brain field to Phase 1 source(s). No source -> INPUT-GAP, never invent.

## 5. Skill Specs

See each `skills/<skill>/SKILL.md`. 2a plan + source-map. 2b founder files (META, hoisted). 2c business files (per-project, no bleed). 2d config split by altitude. 2e 6-dim scoring incl traceability. 2f coherence + master assembly + lock.

## 6. Scoring

Micro: 6-dim (Specificity, Evidence, Differentiation, Actionability, MENA-fit, Traceability). Composite >=9.5, traceability >=9.0, MENA-fit floor 8.0.
Macro: 7 coherence pairs >=9.0 (positioning<->offer, offer<->icp, icp<->gtm, brand-voice<->communication-style, brain<->Phase 1, goals<->project-instruction, MENA+language). Plus multi-project: About-Me once, meta-config once, no drift, no bleed. Phase composite >=9.5.

## 7. Test Plan

Dogfood: Newmind master with Newmind-Coaching (Pro Services) + Newmind-Wellness (Ecom). Shared About-Me + meta-config at Newmind/_customer/. Divergent Project files per project. Cross-project: no business bleed, no About-Me drift.

## 8. Definition of Done

6 skills built. Both Newmind projects Class A. Traceability >=9.0 every file. About-Me + meta-config once at _customer/, no drift. No business bleed. Coherence pairs >=9.0. Zero customer-specific code. Telegram approval tested.

## 9. Risks

Hallucination -> source-map + traceability + INPUT-GAP. Business bleed -> per-project scope + validator check. About-Me drift -> write once + validator. Input gaps -> INPUT-GAP marker. Arabic garbled -> RTL preservation.

## 10. Anti-Patterns (BANNED)

1. Never invent without a Phase 1 source
2. Never hardcode for a customer
3. Never let business bleed across siblings
4. Never ship a brain file <9.5
5. Never skip traceability
6. Never drift from what the customer said
7. Never lock without Telegram approval
8. Never strip Arabic / break RTL
9. Never duplicate About-Me / meta-config with drift
10. Never write meta-config per-project in multi-project mode

## 11. Architect Decisions (Locked)

1. Multi-business via sibling projects, not multi-ICP brains (confirmed: NewMind split into Coaching + Wellness)
2. About-Me + 3 meta-config files SHARED at customer master; Project + project-instruction per-project
3. Traceability = 6th scoring dim (>=9.0), zero-hallucination is Phase 2's core differentiator
4. Source-map mandatory (2a)
5. Brain file set = NewMind-proven structure, adaptive by complexity
6. Composite 9.5, traceability 9.0, MENA-fit floor 8.0
7. Dogfood = Newmind-Coaching + Newmind-Wellness under Newmind master
8. Config splits by altitude (meta to _customer/, project-instruction per project) - the Cowork global+project CLAUDE.md pattern

## 12. Versioning

- v0.1: BRD + 6 skills built
- v0.2 (current): multi-project master mode (altitude split)
- v1.0: both Newmind projects pass, Phase 2 locked
