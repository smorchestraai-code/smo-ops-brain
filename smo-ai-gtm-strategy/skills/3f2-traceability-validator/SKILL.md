---
name: 3f2-traceability-validator
description: "Verifies every asset element citation resolves to an actual brain field. Reads each asset's source-map citations, resolves them against the brain files, flags any unresolvable or fabricated claims. Counts INPUT-GAPs and validates they have honest placeholders, not invented content. Per ADR-001 standard for zero-hallucination. Threshold: >=95% of asset elements have resolvable citations OR are explicitly marked INPUT-GAP."
version: 0.1.0
---

# 3f2-traceability-validator

**Spec:** `phases/phase-3-gtm-strategy-brd.md` Section 5

## Purpose
Enforce zero hallucination. Every asset element either cites a real brain field or is honestly marked INPUT-GAP.

## Inputs
- All assets (with their YAML source citations)
- `2-GTM/output/_asset-source-map.md`
- `1-ProjectBrain/` (the truth set)

## Process
1. For each asset, parse YAML source citations.
2. For each citation:
   a. Resolve against the brain (field exists? value present?)
   b. If resolvable: OK
   c. If unresolvable AND no INPUT-GAP marker: FABRICATION (critical)
   d. If marked INPUT-GAP: count as honest gap
3. Aggregate: % resolved, # INPUT-GAPs, # FABRICATIONs
4. Threshold: 0 fabrications, INPUT-GAPs <=5% of total elements.

## Output
- `2-GTM/output/_scoring/traceability-report.md`

## Self-score
6-dim. Composite >=9.5. The validator itself must be precise.

## Critical Failure
ANY fabrication (unsourced + no INPUT-GAP marker) blocks Phase 3 lock. No exceptions.

## Anti-Patterns
1. Don't tolerate fabrications (zero-tolerance)
2. Don't ignore INPUT-GAPs in the aggregate (they go to operator at Gate 1)
3. Don't pass without resolving every citation

## Handoff
3g cluster (deployment) - only if traceability passes
