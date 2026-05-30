---
name: 3b-sequence-builder
description: "Generates email sequences for a single project, voice-in-context. Loads brand-voice + communication-style + language-preferences + founder voice samples as primary generation context, not post-hoc correction. Cites brain fields per asset element via the asset-source-map. Produces N sequences per the adaptive plan. Use when user runs /gtm-generate or as part of /gtm-build chain."
version: 0.1.0
---

# 3b-sequence-builder

## Purpose
Generate email sequences that sound exactly like the founder, every claim traced to the brain.

## Inputs (voice-in-context primary)
- `1-ProjectBrain/Project/brand-voice.md`
- `1-ProjectBrain/About-Me/communication-style.md`
- `1-ProjectBrain/Config/language-preferences.md`
- `references/voice-samples/*.md` (founder's real content)
- `_asset-source-map.md`, `_playbook-selected.md`
- Brain Project files (offer, icp, positioning, testimonials, faq-objections)

## Process
Per sequence:
1. Load voice context (samples + rules)
2. Load brain inputs per source-map
3. Generate each email with explicit voice cues: signature phrases, forbidden phrases, tone profile
4. Cite brain field per element in YAML frontmatter
5. INPUT-GAP placeholders where no brain source exists; NEVER invent
6. Apply language rules

Write to `2-GTM/output/sequences/<name>/email-N.md`.

## Self-score
6-dim + brand-voice-fit. Composite >=9.5. Traceability >=9.0. MENA-fit floor 8.0.

## Anti-Patterns
1. Don't generate without voice context primary
2. Don't invent (INPUT-GAP markers only)
3. Don't ignore language-preferences
4. Don't include sibling-project content
5. Don't skip per-element source citation

## Handoff
3f-asset-scorer
