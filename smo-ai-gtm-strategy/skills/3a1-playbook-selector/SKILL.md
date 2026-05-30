---
name: 3a1-playbook-selector
description: "Selects 1 primary + 1 secondary GTM playbook from the 13-playbook library based on persona + stage + founder strengths + MENA fit. Adapts the selected playbook's 30-day plan to the customer's brain. Use when user runs /gtm-plan or as part of /gtm-build chain after 3a-gtm-orchestrator."
version: 0.1.0
---

# 3a1-playbook-selector

## Purpose
Pick the right playbook(s) from the 13-library. Adapt to this customer.

## 13 Playbooks
waitlist-heat, build-in-public, authority-education, wave-riding, ltd-cash-to-mrr, signal-sniper, outcome-demo, hammering-feature, bofu-seo, dream-100, 7x4x11, value-trust, paid-vsl.

## Selection Logic
| Persona | Default primary | Secondary |
|---|---|---|
| SaaS early | waitlist-heat | signal-sniper |
| SaaS growth | hammering-feature | bofu-seo |
| Pro Services | authority-education | outcome-demo |
| Enterprise | dream-100 | outcome-demo |
| Ecom | ltd-cash-to-mrr | bofu-seo |

Modifiers: heavy network -> +7x4x11. Content-heavy -> +build-in-public. Long MENA cycle -> value-trust priority. Paid-traffic-ready -> paid-vsl.

## Process
1. Score each of 13 playbooks (fit + MENA fit + founder strength).
2. Pick primary (highest) + secondary.
3. Customize 30-day plan to brain.
4. Write `_playbook-selected.md` with reasoning.

## Output
- `2-GTM/output/_playbook-selected.md`

## Self-score
6-dim. Composite >=9.5. Reasoning cites specific brain signals.

## Anti-Patterns
1. Don't pick generically
2. Don't pick a banned-for-persona playbook
3. Don't ignore MENA fit

## Handoff
3a2-asset-list-planner
