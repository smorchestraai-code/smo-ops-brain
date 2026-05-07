# Source: company-website (Expected Output)

**URL:** file://mock-sources/acme-website.html
**Tool:** Local-mock
**Language detected:** Bilingual
**Arabic dialect:** Gulf Khaleeji
**RTL preserved:** yes
**MENA signals:** Khaleej Times, GCC, UAE-specific (FZ-LLC, AED), Saudi-specific (Tap+HyperPay)

---

## Classifier 1: Company Profile (confidence: 8.4/10)

```yaml
legal_name: Acme-MENATech FZ-LLC
brand_name: Acme-MENATech
founded: 2024
stage: early growth
industry: B2B SaaS
sub_industry: CRM for SMEs
one_line_description: AI-native CRM for MENA SMEs
revenue_model: SaaS subscription, monthly + annual
geographic_focus: [UAE, KSA, Qatar, Kuwait, GCC]
current_state: [200+ customers, Khaleej Times feature, WhatsApp-native, Arabic-native]
```

## Classifier 2: Founder Profile (confidence: 7.8/10)

```yaml
full_name: Layla Al-Rashid
background: [Cisco 12y, Avaya, MENA enterprise sales]
domain_expertise: Enterprise sales MENA, CRM architecture
vision: { one_year: not-found, three_year: not-found }
values_principles: [Build for region not localize from West, Customer-first messaging]
```

## Classifier 3: Offer Signals (confidence: 8.5/10)

```yaml
primary_offer_name: Acme CRM
outcome_promised: AI-native CRM fitting MENA reality
deliverables: [WhatsApp-native, Arabic interface, Tap+HyperPay, 4-day setup]
pricing: { visible: yes, amount: AED 99/seat/month, model: monthly + annual }
differentiation_claims: [40% lower than Salesforce, WhatsApp-native not bolted on, Arabic from day 1]
proof_references: [200+ MENA businesses, 4 named customers, 2 testimonials]
```

## Classifier 4: Brand Voice (confidence: 8.0/10)

```yaml
tone: [confident, contrarian]
archetype: { primary: Outlaw, secondary: Hero }
vocabulary_distinctive: ["Stop forcing your team", "AI-native", "WhatsApp-first", "How MENA actually sells"]
language: Bilingual (English-primary with Arabic testimonial)
arabic_dialect: Gulf Khaleeji
```

## Classifier 5: Proof Signals (confidence: 8.7/10)

```yaml
customer_count_claimed: 200+
notable_customers_named: [GulfRetail Group, Riyadh Telecom Solutions, Doha Medical Centers Network, Kuwait F&B Group]
testimonials: 2 (1 EN + 1 AR with named attribution)
case_studies: [GulfRetail Salesforce migration: 60% cost savings]
press_awards: [Khaleej Times feature March 2026]
years_in_business: ~2
geographic_footprint: [UAE Dubai, KSA, Qatar, Kuwait]
```

---

## Self-Score (5-dim, weighted)

| Dim | Score | Weight | Weighted |
|---|---|---|---|
| Specificity | 9 | 1.0 | 9 |
| Evidence | 9 | 2.0 | 18 |
| Differentiation | 9 | 1.0 | 9 |
| Actionability | 10 | 1.0 | 10 |
| MENA-fit | 10 | 1.5 | 15 |
| **Composite** | | **6.5** | **9.38** |

**MENA-fit floor:** PASS (10≥8)
**Composite:** PASS (9.38≥9.0)
**Status:** pass
