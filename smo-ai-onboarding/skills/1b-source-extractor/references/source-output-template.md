# Source: <SOURCE_TYPE>

**URL:** <url>
**Scraped:** <date>
**Tool:** <Chrome MCP / Firecrawl / Playwright / Local-mock>
**Language detected:** <English / Arabic / Bilingual>
**Arabic dialect:** <if applicable>
**RTL preserved:** <yes/no>
**MENA signals:** <list>

---

## Classifier 1: Company Profile (confidence: <X>/10)
```yaml
legal_name: <value or not-found>
brand_name:
founded:
stage:
industry:
revenue_model:
geographic_focus:
current_state:
confidence_per_field: { ... }
quotes: [{ field, quote }]
```

## Classifier 2: Founder Profile
```yaml
full_name:
background: []
domain_expertise:
vision: { one_year, three_year }
operating_style_signals: []
communication_style_signals: []
values_principles: []
```

## Classifier 3: Offer Signals
```yaml
primary_offer_name:
outcome_promised:
deliverables: []
pricing: { visible, amount, model }
tiers: []
differentiation_claims: []
proof_references: []
```

## Classifier 4: Brand Voice
```yaml
tone:
archetype: { primary, secondary }
vocabulary_distinctive: []
what_they_say: []
what_they_dont_say: []
language:
arabic_dialect:
```

## Classifier 5: Proof Signals
```yaml
customer_count_claimed:
notable_customers_named: []
testimonials: []
case_studies: []
press_awards: []
years_in_business:
revenue_claims:
geographic_footprint: []
verification_status: { ... }
```

---

## Self-Score (5-dim, weighted)
| Dim | Score | Weight | Weighted |
|---|---|---|---|
| Specificity | X | 1.0 | X |
| Evidence | X | 2.0 | 2X |
| Differentiation | X | 1.0 | X |
| Actionability | X | 1.0 | X |
| MENA-fit | X | 1.5 | 1.5X |
| **Composite** | | **6.5** | **<sum/6.5>** |

MENA-fit floor check: PASS if ≥8.
Composite threshold: PASS if ≥9.0.
Status: pass / gap-fill-loop / escalate.
