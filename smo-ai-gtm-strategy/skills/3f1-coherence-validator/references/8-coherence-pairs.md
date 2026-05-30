# 8 Phase-3 Coherence Pairs (detailed spec)

Each pair is LLM-driven semantic comparison, scored 0-10. All >=9.0 to pass Phase 3 lock.

## Pair 1: welcome-sequence-voice <-> brand-voice
Sources: `sequences/welcome/*.md` and `1-ProjectBrain/Project/brand-voice.md`
Test: Do the welcome emails sound like the brand voice? Signature phrases present? Forbidden phrases absent? Tone match?
Pass: 10 = indistinguishable from founder's real samples. <8 = generic voice.

## Pair 2: funnel-cta <-> offer.outcome-promised
Sources: `funnels/*/main.md` CTAs and `offer.md`
Test: Does the CTA promise what the offer delivers? No bait-and-switch.
Pass: 10 = perfect alignment. <8 = CTA over-promises or vague.

## Pair 3: whatsapp-tone <-> communication-style per-channel
Sources: `whatsapp/*.md` and `communication-style.md` (per-channel rules)
Test: Does WhatsApp respect the channel-specific tone (Arabic-first Khaleeji for MENA, less formal than email)?
Pass: 10 = channel-appropriate. <8 = wrong channel tone (e.g., formal email tone on WhatsApp).

## Pair 4: landing-positioning <-> positioning.md
Sources: `content/landing/*.md` hero/value-prop and `positioning.md`
Test: Does the landing page lead with the positioning statement? Differentiation clear?
Pass: 10 = positioning is the headline. <8 = generic landing.

## Pair 5: email-frequency <-> MENA cultural calendar
Sources: sequence schedules (send times/days) and MENA-Calendar config
Test:
- No 11pm sends during Ramadan
- No major campaign launches Eid weeks (Al-Fitr, Al-Adha, Mawlid)
- Friday low-send-volume (GCC weekend)
- Prayer times honored in WhatsApp windows
- National day awareness
Pass: 10 = all rules respected. <8 = any rule violated.

## Pair 6: price-presentation <-> pricing-strategy + faq-objections
Sources: `funnels/*/main.md` pricing sections + `sequences/*/email-N.md` price mentions, vs `pricing-strategy.md` and `faq-objections.md`
Test: Does pricing presentation match the strategy? Are objections handled where price appears?
Pass: 10 = aligned + objections handled. <8 = price mentioned without objection handling.

## Pair 7: testimonials-used <-> testimonials.md (verified only)
Sources: every testimonial citation in any asset, vs `testimonials.md`
Test: Is every cited testimonial in testimonials.md? Is it verified (not just claimed)?
Pass: 10 = every testimonial verified. <8 = any unverified or fabricated testimonial = critical fail.

## Pair 8: playbook-30-day-plan <-> current-priority-project KPIs
Sources: `_playbook-selected.md` 30-day plan and `current-priority-project.md` KPIs
Test: Does the 30-day plan move the KPI needle? Are the right activities prioritized?
Pass: 10 = plan directly serves KPI. <8 = plan and KPIs disconnected.

## No Business Bleed (separate check)
For multi-project customers: scan each project's assets for references to sibling projects' businesses.
Test: Newmind-Coaching assets must contain only coaching content. Wellness references in coaching assets = bleed.
Critical fail = ANY bleed.
