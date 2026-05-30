---
name: 3e-content-builder
description: "Generates landing pages, LinkedIn posts, YouTube outlines for a single project, voice-in-context. The brand-slice content layer per the playbook 30-day plan. Cites brain fields per element. Respects language-preferences per-channel split. Use when user runs /gtm-generate or as part of /gtm-build chain."
version: 0.1.0
---

# 3e-content-builder

## Purpose
Generate the brand-slice content layer.

## Inputs (voice-in-context primary)
- Voice context (3b/3c/3d)
- `_asset-source-map.md`, `_playbook-selected.md`
- Brain: content-guidelines, positioning, brand-voice

## Process
Per piece:
1. Landing pages: hero (positioning), social proof, value-prop, CTA, FAQ (multi-section, mobile-first)
2. LinkedIn: hook (first 7 words highest leverage), body, CTA (Track A AR or Track B EN per language-preferences)
3. YouTube: title, hook, sections, B-roll, CTA
4. Source-cite per element

Write to `2-GTM/output/content/{landing,linkedin,youtube}/<name>.md`.

## Self-score
6-dim + brand-voice-fit. Composite >=9.5. Per channel hook-strength check.

## Anti-Patterns
1. Don't write generic content
2. Don't ignore Track A / Track B for LinkedIn
3. Don't skip hook-strength check
4. Don't invent stats (cite brain or INPUT-GAP)
5. Don't bypass voice samples

## Handoff
3f-asset-scorer
