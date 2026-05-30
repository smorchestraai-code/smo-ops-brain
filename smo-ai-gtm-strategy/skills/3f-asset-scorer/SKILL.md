---
name: 3f-asset-scorer
description: "Scores every generated asset on type-specific rubrics. Email sequences get email-specific 6-dim (subject strength, body voice, CTA clarity, etc.). Funnels get funnel-specific (page hierarchy, CTA conversion logic, mobile rendering). WhatsApp gets Meta-compliance + dialect. Content gets hook-strength + channel-fit. All assets get the standard 6-dim plus brand-voice-fit (samples comparison). Composite >=9.5 per asset. Use after generators complete, as part of /gtm-build or via /gtm-score."
version: 0.1.0
---

# 3f-asset-scorer

**Spec:** `phases/phase-3-gtm-strategy-brd.md` Section 15

## Purpose
Score every asset. Type-specific rubrics. Enforce thresholds.

## Inputs
- All assets in `2-GTM/output/sequences/`, `funnels/`, `whatsapp/`, `content/`
- `1-ProjectBrain/Project/brand-voice.md`, `communication-style.md`, voice-samples

## Per-Type Rubrics

### Email sequence
6-dim + email-specific:
- Subject strength (open-rate predictor)
- Body voice fit (samples comparison)
- CTA clarity
- Personalization depth
- Length appropriate to sequence stage

### Funnel
6-dim + funnel-specific:
- Page hierarchy clarity
- CTA primacy (single primary CTA per page)
- Mobile rendering (no horizontal scroll, tap targets >=44px)
- Conversion logic (opt-in -> sales -> thank-you, no friction)
- Auto-tagging logic complete

### WhatsApp
6-dim + WhatsApp-specific:
- Meta category compliance
- Variable syntax correct
- Dialect appropriate (Khaleeji for Sam)
- Character limits respected
- Time-window awareness (no 11pm sends config)

### Content (landing/LinkedIn/YouTube)
6-dim + content-specific:
- Hook strength (first 7 words score)
- Channel-fit (LinkedIn != YouTube != Landing)
- Track A/B for LinkedIn (Arabic vs English)
- Source citation depth

## Process
1. For each asset: load type-specific rubric.
2. Score 6-dim + type-specific dimensions.
3. Voice-fit comparison: compare asset against founder voice samples (semantic similarity + signature phrase usage).
4. Write per-asset score block + aggregate to `_scoring/per-asset-scores.md`.
5. Identify low-scorers, trigger gap-fill loop.

## Output
- `2-GTM/output/_scoring/per-asset-scores.md`

## Self-score
6-dim. Composite >=9.5 (the scorer itself must be defensible).

## Anti-Patterns
1. Don't apply one rubric across all asset types
2. Don't skip voice-fit comparison
3. Don't lock with any asset <9.5

## Handoff
3f1-coherence-validator, 3f2-traceability-validator, then 3g cluster
