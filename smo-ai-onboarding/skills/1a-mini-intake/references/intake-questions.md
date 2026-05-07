# Intake Questions (Reference)

Structured form for AskUserQuestion tool. See SKILL.md for full schema.

## Q1: Customer Identity
- field: founder_name (required)
- field: brand_name (optional)
- field: primary_url (required, must validate as URL)

## Q2: Project Structure
- single OR multi (if multi, list project names + URLs)

## Q3: Persona
- SaaS / Pro Services / Enterprise / Ecom (single-select, required)
- Anti-pattern: never auto-detect from URL

## Q4: Build Priority
- Rank: Ops, GTM, Social, Others (default: Ops > GTM > Social > Others)
- If Others priority 1-2: ask scope (SEO/training/HR/custom)

## Q5: Language Preference
- Arabic (with dialect: Gulf Khaleeji, Egyptian, Levantine, MSA, Mix)
- English
- Bilingual (with primary + per-channel split)

## Compaction

Single-project: 1-2 AskUserQuestion calls (batched).
Multi-project: Q1+Q2 first, then Q3+Q4+Q5 per project.
