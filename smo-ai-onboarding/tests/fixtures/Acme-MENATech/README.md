# Test Fixture: Acme-MENATech

**Type:** Synthetic (no real customer data)
**Purpose:** Validate Phase 1 skills end-to-end without internet or real-customer risk.

## Fixture Profile

- **Founder:** Layla Al-Rashid (fictional)
- **Company:** Acme-MENATech (fictional UAE B2B SaaS)
- **Persona:** SaaS
- **Multi-project:** No
- **Language:** Bilingual (English primary, Arabic for customer comms)
- **Build priority:** GTM > Ops > Social > Others
- **Industry:** B2B SaaS for MENA SMEs
- **Stage:** Early growth

## URLs (file:// for local-mock)

- Website: `file://mock-sources/acme-website.html`
- LinkedIn: `file://mock-sources/layla-linkedin.md`

## Edge Cases Engineered

1. Arabic content (RTL preservation test)
2. Mixed Arabic + English in LinkedIn (bilingual test)
3. Missing personal site URL (not-found handling)
4. Pricing partially hidden (confidence per-field test)
5. Brand voice mismatch (cross-source coherence flag)
6. MENA signals (Khaleej Times, GCC, Tap+HyperPay, FZ-LLC)
7. PII placeholders (false positive test)
8. Code-switched Arabic posts in Khaleeji (dialect test)

## Files

- README.md (this file)
- inputs/persona-and-priority.md (pre-filled, simulates 1a output)
- mock-sources/acme-website.html
- mock-sources/layla-linkedin.md
- expected-outputs/sources-company-website.md
- expected-outputs/sources-founder-linkedin.md
- expected-outputs/_first-input-layer.md
- test-runner.md

## Pass Criteria

- All source files generated, scored ≥9.0 composite
- _first-input-layer.md synthesis ≥9.0
- MENA-fit ≥8.0 across all
- Cross-source coherence flag for brand voice variance
- No PII fabricated
- No customer-specific code (anti-pattern scan clean)
