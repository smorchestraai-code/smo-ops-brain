# Phase 3 BRD: GTM Strategy + Assets + Deployment

**Plugin:** smo-ai-gtm-strategy
**Status:** v0.1 (BRD locked, 19 skills built)
**Date:** 2026-05-30
**Composite target:** 10/10

See plugin SKILL.md files for skill specs. Key design decisions:

## Hard Rules
- Zero hallucination via asset-source-map (every asset element cites a brain field)
- Voice-in-context generation (brand-voice + communication-style + founder voice samples = primary)
- No business bleed across sibling projects
- Staged trigger (test -> small -> full)
- 3 Telegram gates (pack, trigger, scale) per ADR-001

## Architect Decisions (Locked)
1. Asset-source-map is mandatory (anti-hallucination spine)
2. Asset counts adaptive (driven by persona + complexity, not customer-baked)
3. 13-playbook library is the strategic frame (3a1 selects)
4. 8 coherence pairs validated by 3f1
5. Voice-in-context generation (not generate-then-score)
6. Deploy split into 7 per-GHL-surface skills
7. 3 Telegram gates with full specs (shown/asked/default/escalation)
8. Staged rollout inside Gate 2 (test -> small -> full)
9. Everything project-level
10. Bilingual EN/AR + MENA calendar awareness
11. Command quartet standard (gtm-start canonical)
12. Phase 4 handoff schema defined upfront

## Test Plan (Dogfood)
Newmind-Coaching + Newmind-Wellness. Compare against MicroPlan Asset Register (Sam's manually-built baseline). Pass when: matching or superior asset count, voice fit >=8.5, traceability >=95%, coherence pairs >=9.0, deployment successful, smoke test green, staged trigger executes through Gate 3.

## Versioning
- v0.1 (current): BRD + 19 skills built
- v1.0: Newmind dogfood passes
