---
name: 1b-source-extractor
description: "Auto-scrapes customer URLs (website, LinkedIn, social profiles) using Chrome MCP, Firecrawl, or Playwright per URL type. Runs 5 information-target classifiers per source and produces first input layer for downstream skills. Use when user runs /onboarding-extract or after 1a mini-intake locks."
version: 0.1.0
---

# 1b-source-extractor (Sub-step 1.B)

**Status:** v0.1 BUILT
**Phase:** 1 (Input Capture)
**Spec source:** `phases/phase-1-input-capture-brd.md` Section 5.2

## Purpose

Auto-scrape customer URLs and produce structured first input layer that informs 1c (memory prompts) and 1d (files request).

## Triggers

- `/onboarding-extract <customer-folder>`
- `/onboarding-extract <customer-folder> --rerun`
- Auto-trigger from `/onboarding-guide` after 1a locks

## Process (10 steps)

1. Pre-check (verify persona-and-priority.md exists and locked)
2. URL discovery (per-URL type detection)
3. Scraper selection + execution (Chrome MCP / Firecrawl / Playwright / Local-mock)
4. Language detection on raw content
5. RTL preservation for Arabic
6. Run 5 classifiers per source (parallel)
7. Write per-source output files
8. Synthesize first input layer (cross-source aggregation)
9. PII scan
10. Self-score per file + handoff

## 5 Classifiers

1. **company-profile**: legal name, brand, founded, stage, industry, revenue model, geography
2. **founder-profile**: name, background, vision, operating style, communication style, principles
3. **offer-signals**: name, outcome, deliverables, pricing, tiers, differentiation, proof
4. **brand-voice**: tone, archetype, vocabulary, what they say, what they don't say, language + dialect
5. **proof-signals**: customers, testimonials, case studies, press, years, geographic footprint

## Outputs

- `0-Input/sources/<source-type>.md` per URL
- `0-Input/sources/_first-input-layer.md` synthesis
- `0-Input/sources/_raw/<source-type>-raw.md` audit trail
- `_security/pii-findings.md` if PII detected

## Self-score Rubric

See `references/rubric.md`. Weighting: Evidence 2.0x, MENA-fit 1.5x, others 1.0x. Threshold ≥9.0. MENA-fit floor 8.0.

## Anti-Patterns

1. Don't infer persona from URL
2. Don't fabricate signals
3. Don't strip Arabic content
4. Don't extract PII silently
5. Don't skip failed sources without logging
6. Don't combine signals across sources in per-source files
7. Don't auto-translate Arabic

## Handoff

Next: `1c-memory-prompter` AND `1d-files-requester` (parallel)

## Test

`tests/fixtures/Acme-MENATech/`. Run via `/onboarding-extract Acme-MENATech --test-mode`.

## Version

v0.1 (2026-05-06)
