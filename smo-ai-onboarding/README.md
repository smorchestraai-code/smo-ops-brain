# smo-ai-onboarding (Plugin)

Universal Layer A plugin. Master onboarding plugin that converts customer inputs into structured brain context, GTM strategy, and customer-specific plugin BRDs.

**Version:** 0.5.0
**Status:** Phase 1 fully built. Ready for Acme stress test.

## Phase 1: Input Capture (BUILT v0.5)

Full BRD: `phases/phase-1-input-capture-brd.md`

| Sub-step | Skill | Status | Command |
|---|---|---|---|
| 1.A Mini-intake | `1a-mini-intake` | BUILT | `/onboarding-start` (canonical) |
| 1.B Source extraction | `1b-source-extractor` | BUILT | `/onboarding-extract` |
| 1.C Memory mining | `1c-memory-prompter` | BUILT | `/onboarding-memory` |
| 1.D Files request | `1d-files-requester` | BUILT | `/onboarding-files` |
| 1.E Interview | `1e-interview-generator` | BUILT | `/onboarding-interview` |
| 1.F Validation + lock | `1f-input-validator` | BUILT | `/onboarding-validate` |

## Universal Commands

- `/onboarding-start <customer>` - canonical entry, creates scaffold, runs 1a
- `/onboarding-guide [<customer>]` - copilot, recommends next action
- `/onboarding-status [<customer>]` - dashboard

## Build Discipline

- Generic plugin. Works for ANY customer.
- Tested on synthetic Acme-MENATech first, then Sam (NewMind + Chaga).
- Sam inputs do NOT shape plugin design.
- Phase tested as coherent outcome, not skill-by-skill.

## Folder Layout

```
smo-ai-onboarding/
├── .claude-plugin/plugin.json
├── README.md
├── commands/ (8 commands)
├── phases/phase-1-input-capture-brd.md
├── skills/ (6 skills with references/)
├── recovery/ (state recovery + anti-pattern scanner)
└── tests/fixtures/Acme-MENATech/ (synthetic stress test)
```

## Scoring

Micro: per-skill self-score, 5-dim rubric, ≥9.0 to ship. MENA-fit floor 8.0.
Macro: 1f-input-validator runs phase-level coherence (7 pairs ≥9.0). Phase composite ≥9.5.

## Anti-Pattern Enforcement

3-layer: pre-commit grep, anti-pattern-scanner skill, manual code review. 15 banned patterns.

## Test Fixture

`tests/fixtures/Acme-MENATech/` - synthetic SaaS founder Layla Al-Rashid, bilingual EN/AR, with engineered edge cases (RTL, MENA signals, brand voice variance).

Sam stress test happens AFTER Acme passes.
