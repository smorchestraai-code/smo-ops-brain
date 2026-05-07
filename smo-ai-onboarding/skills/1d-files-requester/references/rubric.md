# Scoring Rubric (1d-files-requester)

Weighting: Evidence 1.5x, Actionability 1.5x, MENA-fit 1.5x, others 1.0x.

## Specificity (1.0x)
10: Persona-customized list. <8: generic boilerplate.

## Evidence (1.5x)
10: Every signal traces to file section. <8: fabrication.

## Differentiation (1.0x)
10: Persona-specific requests. <8: same list across personas.

## Actionability (1.5x)
10: Extracted text parsable downstream. <8: unstructured noise.

## MENA-fit (1.5x, FLOOR 8.0)
10: Arabic OCR + RTL + dialect detected. <8: Arabic garbled.

## Composite
```
weighted_sum = (1.0*spec) + (1.5*evidence) + (1.0*diff) + (1.5*action) + (1.5*mena)
weight_total = 6.5
composite = weighted_sum / weight_total
```
Threshold: ≥9.0.
