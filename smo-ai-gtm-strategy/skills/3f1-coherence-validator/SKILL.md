---
name: 3f1-coherence-validator
description: "Validates 8 phase-level coherence pairs across all generated assets: welcome-sequence-voice vs brand-voice, funnel-cta vs offer.outcome-promised, whatsapp-tone vs communication-style per-channel, landing-positioning vs positioning.md, email-frequency vs MENA cultural calendar (Ramadan, Eid, prayer times), price-presentation vs pricing-strategy + faq-objections, testimonials-used vs verified testimonials.md, playbook-30-day-plan vs current-priority-project KPIs. Plus no business bleed across sibling projects. Each pair >=9.0 to pass phase lock. Use after 3f-asset-scorer."
version: 0.1.0
---

# 3f1-coherence-validator

**Spec:** `phases/phase-3-gtm-strategy-brd.md` Section 6

## Purpose
Validate 8 coherence pairs + no-business-bleed.

## 8 Pairs (each >=9.0)
1. welcome-sequence-voice <-> brand-voice
2. funnel-cta <-> offer.outcome-promised
3. whatsapp-tone <-> communication-style per-channel rules
4. landing-positioning <-> positioning.md
5. email-frequency <-> MENA cultural calendar
6. price-presentation <-> pricing-strategy + faq-objections
7. testimonials-used <-> testimonials.md (verified only)
8. playbook-30-day-plan <-> current-priority-project KPIs

Plus: no business bleed (multi-project: each project's assets contain only that project's business content).

## MENA Calendar Awareness (Pair 5)
Loads MENA-Calendar config. Enforces:
- No 11pm sends during Ramadan
- No major campaign launches Eid weeks (Al-Fitr, Al-Adha)
- Friday low-send-volume (GCC)
- Prayer times honored in WhatsApp windows
- National day awareness per market

## Process
1. For each of 8 pairs:
   a. Load both sides (assets + brain reference)
   b. LLM-driven semantic comparison
   c. Score 0-10
2. No-business-bleed check: scan each asset for sibling-project references
3. Write per-pair scores + discrepancies + resolution paths

## Output
- `2-GTM/output/_scoring/coherence-pairs.md`

## Self-score
6-dim. Composite >=9.5.

## Anti-Patterns
1. Don't surface-match (semantic check required)
2. Don't ignore MENA calendar (Pair 5 is mandatory)
3. Don't pass with business bleed

## Handoff
3f2-traceability-validator
