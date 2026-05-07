# Scoring Rubric (1b-source-extractor)

Weighting: Evidence 2.0x, MENA-fit 1.5x, others 1.0x.

## Specificity (1.0x)
10: All 5 classifiers return concrete signals. <5: classifiers found nothing usable.

## Evidence (2.0x)
10: Every signal traces to source quote. <5: fabrication detected (CRITICAL).

## Differentiation (1.0x)
10: Source-specific signals. <5: all template defaults.

## Actionability (1.0x)
10: 1c+1d can proceed without further inference. <5: unusable downstream.

## MENA-fit (1.5x, FLOOR 8.0)
10: Arabic + dialect + RTL + MENA signals captured. <7: Arabic missed.

## Composite
```
weighted_sum = (specificity * 1.0) + (evidence * 2.0) + (differentiation * 1.0) + (actionability * 1.0) + (mena_fit * 1.5)
weight_total = 6.5
composite = weighted_sum / weight_total
```
Threshold: ≥9.0. Max 3 gap-fill retries.
