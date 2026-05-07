# Memory Extract: <topic>

**Customer:** <name>
**Source dump:** `references/llm-extracts/<topic>-<date>.md`
**Extracted:** <date>
**Language detected:** <en/ar/bilingual>
**Dedup against 1b:** <count of duplicates removed>

---

## Structured Signals

[YAML structure per topic - see SKILL.md]

For offer-deep-dive: pricing_logic, hidden_features, demo_flow, upsell_logic, discount_triggers, contract_norms, deprecated_offer_elements.
For communication-style: opening_lines, elevator_pitch, signature_phrases, forbidden_phrases, tone_shifts, signature_signoff.
For customer-conversations: list of {customer_role, industry, mena_region, question, response, outcome, learning}.
For sales-history: list of {context, deal_size, sales_cycle_days, interest_driver, key_objections, outcome, learning}.
For operating-preferences: daily_routine, decision_style, energy_patterns, tools, update_preferences, non_negotiables.
For network-and-advisors: inner_circle, mentors, peer_founders, advisors.

Every extract: confidence_per_field, quotes (max 30 words each).

## Self-Score (5-dim with 1c weighting)

Composite ≥9.0 required.
