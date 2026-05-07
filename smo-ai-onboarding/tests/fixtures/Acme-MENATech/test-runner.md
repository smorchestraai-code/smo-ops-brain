# Test Runner: 1b-source-extractor on Acme-MENATech

## Setup

1. Create test customer folder: `clients-onboarding/Acme-MENATech-test/`
2. Copy state-0 scaffold
3. Copy `inputs/persona-and-priority.md` to `Acme-MENATech-test/0-Input/`

## Execution

```
/onboarding-extract Acme-MENATech-test --test-mode
```

Skill should: read persona-and-priority.md, detect 2 file:// URLs, use Local-mock scraper, run 5 classifiers per source, write structured outputs, synthesize first-input-layer, self-score.

## Assertions

### File Existence
- `0-Input/sources/company-website.md`
- `0-Input/sources/founder-linkedin.md`
- `0-Input/sources/_first-input-layer.md`
- `0-Input/sources/_raw/company-website-raw.md`
- `0-Input/sources/_raw/founder-linkedin-raw.md`

### Score Thresholds
- Each source file composite ≥9.0
- _first-input-layer.md composite ≥9.0
- All MENA-fit ≥8.0
- All Evidence ≥7.0

### Content Validation
- Founder name: Layla Al-Rashid
- Company: Acme-MENATech
- Persona-aligned (SaaS) signals
- Arabic dialect: Gulf Khaleeji
- RTL preserved
- MENA signals: Khaleej Times, GCC, Tap+HyperPay, FZ-LLC

### Cross-Source Coherence
- _first-input-layer.md flags brand voice variance (website Outlaw vs LinkedIn Sage)
- Identifies vision gap for 1c
- Identifies pricing detail gap for 1d
- Identifies tool inventory gap for 1e

### PII Handling
- No PII fabricated
- Phone placeholder (+971-50-XXX-XXXX) detected
- Email placeholder (.example) flagged

### Anti-Pattern Scan
- No customer-specific code
- No "Layla" or "Acme" hardcoded outside test fixture folder

## Pass Criteria

ALL assertions pass → 1b v0.1 PASSES Acme test.

Failure: identify generic gap, fix in skill, re-run, loop until all pass.

## Sam Stress Test

Deferred until ALL 6 sub-steps (1a-1f) pass Acme. This avoids partial-skill testing on real customers.
