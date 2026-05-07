---
name: 1a-mini-intake
description: "Captures 5 essential customer onboarding questions (identity, project structure, persona, build priority, language preference) and instantiates customer scaffold from state-0. First skill in Phase 1 input capture chain. Use when user runs /onboarding-start or asks to begin a new customer onboarding session."
version: 0.1.0
---

# 1a-mini-intake (Sub-step 1.A of Build Step 1)

## Purpose

Capture 5 essential questions at customer onboarding session start and instantiate the customer's working folder. Output sets the routing for all downstream phases.

This is a GENERIC skill. It must NOT contain customer-specific logic. Same skill runs for SaaS founders, professional service providers, enterprise B2B, and ecom DTC brands.

## Triggers

- `/onboarding-start <customer-folder-name>`
- "start onboarding for <customer>"
- "onboard a new customer"
- "set up new customer"
- "new client intake"
- "begin customer onboarding"

## Inputs (5 questions)

1. Customer Identity (founder name + brand name + primary URL)
2. Project Structure (single or multi-project)
3. Persona (SaaS / Pro Services / Enterprise / Ecom)
4. Build Priority (rank Ops, GTM, Social, Others)
5. Language Preference (Arabic / English / Bilingual)

## Process

1. Verify or create customer folder from state-0 scaffold
2. Ask 5 questions via AskUserQuestion
3. Write `0-Input/persona-and-priority.md`
4. Initialize `tracker.md`
5. Update `_progress.md`
6. Self-score (5-dim, threshold ≥9.0)
7. Hand off to 1b-source-extractor

## Output

- `<customer-folder>/0-Input/persona-and-priority.md` (filled, ≥9.0)
- `<customer-folder>/tracker.md` (Phase 0a in-progress)
- `<customer-folder>/_progress.md` (status updated)

## Self-Score Rubric

See `references/scoring-rubric.md`. 5-dim: Specificity, Evidence, Differentiation, Actionability, MENA-fit. MENA-fit floor 8.0 mandatory.

## Anti-Patterns

- DO NOT hardcode customer-specific data
- DO NOT skip questions
- DO NOT assume persona from URL pattern
- DO NOT default to English without confirming
- DO NOT copy state-0 scaffold over a populated customer folder

## Handoff

Next: `1b-source-extractor` via `/onboarding-guide` or `/onboarding-extract`

## Stress Test

After ship: run on Sam-NewMind + Sam-Chaga, score outputs, fix generic gaps, lock when both pass.

## Version

v0.1.0 (2026-05-06)
