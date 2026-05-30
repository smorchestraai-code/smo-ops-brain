---
name: 3d-whatsapp-builder
description: "Generates WhatsApp templates for a single project, voice-in-context and dialect-aware. Produces Meta-template-ready content (categories TRANSACTIONAL / MARKETING / AUTHENTICATION, variable syntax, char limits). Respects per-channel language split from language-preferences (Arabic-first Khaleeji is the MENA default). Use when user runs /gtm-generate or as part of /gtm-build chain."
version: 0.1.0
---

# 3d-whatsapp-builder

## Purpose
Generate Meta-approval-ready WhatsApp templates in the right dialect.

## Inputs (voice-in-context primary)
- Voice context (3b/3c)
- language-preferences (per-channel; MENA default: WhatsApp Arabic-first)
- `_asset-source-map.md`
- Brain: offer, icp

## Meta Template Rules
- Categories: TRANSACTIONAL / MARKETING / AUTHENTICATION
- No links in AUTHENTICATION body
- Variables: `{{1}}` `{{2}}`
- No promotional language in TRANSACTIONAL
- Approval cycle 12-72h

## Process
Per template:
1. Determine category
2. Generate in customer's WhatsApp language (Khaleeji for Sam)
3. Use arabic-translator skill for EN -> AR with bidi isolation
4. Verify Meta rules
5. Source-cite per element

Write to `2-GTM/output/whatsapp/<name>.md` (Meta-submission-ready).

## Self-score
6-dim + brand-voice-fit + Meta-compliance. Composite >=9.5. MENA-fit floor 8.5.

## Anti-Patterns
1. Don't write in English if customer language is Arabic-primary
2. Don't violate Meta category rules
3. Don't use latinized Arabic (Arabic script only)
4. Don't ignore prayer-time / Friday rules
5. Don't bypass arabic-translator for AR

## Handoff
3f-asset-scorer
