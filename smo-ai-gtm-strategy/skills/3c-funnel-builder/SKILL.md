---
name: 3c-funnel-builder
description: "Generates funnels for a single project, voice-in-context. Builds opt-in pages, sales pages, thank-you/upsell pages, and auto-tagging logic per funnel. Cites brain fields per element via the asset-source-map. Produces N funnels per the adaptive plan. Use when user runs /gtm-generate or as part of /gtm-build chain."
version: 0.1.0
---

# 3c-funnel-builder

## Purpose
Generate funnels (multi-page flows) per the planned list.

## Inputs (voice-in-context primary)
- Same voice context as 3b (brand-voice, communication-style, language-preferences, samples)
- `_asset-source-map.md` per funnel
- Brain: offer, positioning, pricing-strategy, testimonials (verified), icp

## Process
Per funnel:
1. Generate opt-in page (hero, value-prop, form)
2. Generate sales/main page (offer, proof, pricing, CTA, objection handling)
3. Generate thank-you / upsell page
4. Define auto-tagging logic
5. Source-cite every element

Write to `2-GTM/output/funnels/<name>/{opt-in.md, main.md, thank-you.md, auto-tagging.md}`.

## Self-score
6-dim + brand-voice-fit. Composite >=9.5.

## Anti-Patterns
1. Don't write generic landing copy
2. Don't invent pricing (pricing-strategy.md only)
3. Don't include unverified testimonials
4. Don't bypass voice context
5. Don't omit auto-tagging (deployer needs it)

## Handoff
3f-asset-scorer
