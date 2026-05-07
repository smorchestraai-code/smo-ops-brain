# Scoring Rubric (1f-input-validator)

Weighting: Evidence 1.5x, Actionability 1.5x, others 1.0x.

## Specificity (1.0x)
10: Validation pinpoints files, dims, contradictions. <9: vague pass/fail.

## Evidence (1.5x)
10: Every conclusion traces to file + rubric criterion. <9: not traceable.

## Differentiation (1.0x)
10: Coherence catches semantic discrepancies. <9: surface-level word match.

## Actionability (1.5x)
10: Lock/loop hints immediately actionable. <9: vague "needs more work".

## MENA-fit (1.0x, FLOOR 8.0)
10: Floor verified across ALL files. <8: floor enforcement skipped.

## Composite
```
weighted_sum = (1.0*spec) + (1.5*evidence) + (1.0*diff) + (1.5*action) + (1.0*mena)
weight_total = 6.0
composite = weighted_sum / weight_total
```
Threshold: ≥9.0.
