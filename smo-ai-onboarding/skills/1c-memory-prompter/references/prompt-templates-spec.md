# Prompt Templates Spec

7 base prompts in `_templates/Memory-Mining-Prompts/`. Each in 3 language variants (en, ar, bilingual).

## Templates

1. **offer-deep-dive**: pricing logic, hidden features, demo flow, upsell logic, contract norms
2. **communication-style**: opening lines, signature phrases, tone shifts per channel
3. **customer-conversations**: 5 most recent conversations verbatim with outcomes
4. **sales-history**: 10 deals (won/lost) with reasons and learnings
5. **operating-preferences**: daily routine, decision style, energy patterns, tools
6. **network-and-advisors**: inner circle, mentors, peer founders
7. **persona-specific-deep-dive**: SaaS roadmap / Pro Services lifecycle / Enterprise procurement / Ecom ops

## Selection Logic

Always: customer-conversations, sales-history, operating-preferences, persona-specific.
Conditional: skip offer-deep-dive if 1b offer-signals ≥9.0; skip communication-style if 1b brand-voice ≥9.5; skip network for solo founder.

Default: 5-7 prompts.
