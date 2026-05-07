# Scoring Rubric (1c-memory-prompter)

Weighting: Specificity 1.5x, Evidence 1.5x, Differentiation 1.5x, Actionability 1.0x, MENA-fit 1.5x.

## Specificity (1.5x)
10: Prompts named brand/founder/offer. <7: mostly generic.

## Evidence (1.5x)
10: Every signal traces to dump. <7: fabrication (CRITICAL).

## Differentiation (1.5x)
10: Prompts go beyond vanilla. <7: prompts could be answered from website (anti-pattern).

## Actionability (1.0x)
10: Extracts directly usable downstream. <7: needs manual interpretation.

## MENA-fit (1.5x, FLOOR 8.0)
10: Customer's language + dialect + RTL preserved. <8: language mismatch.

## Composite
```
weighted_sum = (specificity*1.5) + (evidence*1.5) + (differentiation*1.5) + (actionability*1.0) + (mena_fit*1.5)
weight_total = 7.0
composite = weighted_sum / weight_total
```
Threshold: ≥9.0 per extract.
