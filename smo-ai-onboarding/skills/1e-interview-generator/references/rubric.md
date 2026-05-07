# Scoring Rubric (1e-interview-generator)

Weighting: Actionability 2.0x, Specificity 1.5x, Differentiation 1.5x, MENA-fit 1.5x, Evidence 1.0x.

## Specificity (1.5x)
10: Every question concrete, anchored to known signal. <8: vague "tell me about".

## Evidence (1.0x)
10: Each answer anchored to example/data. <8: hand-wavy.

## Differentiation (1.5x)
10: Beyond what 1b/1c/1d already captured. <8: redundancy with prior layers.

## Actionability (2.0x)
10: Output unblocks Phase 2 immediately. <8: Phase 2 blocked.

## MENA-fit (1.5x, FLOOR 8.0)
10: Customer's preferred language + dialect. Cultural anchors respected. <8: language mismatch.

## Composite
```
weighted_sum = (1.5*spec) + (1.0*evidence) + (1.5*diff) + (2.0*action) + (1.5*mena)
weight_total = 7.5
composite = weighted_sum / weight_total
```
Threshold: ≥9.0.
