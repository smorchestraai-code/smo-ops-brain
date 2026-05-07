# Coherence Pairs Specification

7 pairs validated by 1f Stage C. LLM-driven semantic comparison.

## Pair 1: 1a persona <-> 1b source signals
Does 1b confirm declared persona? Mismatch: declared SaaS but project-based revenue.

## Pair 2: 1b brand-voice <-> 1c communication-style memory
Founder's articulated voice match public voice? Channel-specific variance flag.

## Pair 3: 1b offer-signals <-> 1c offer-extract
Internal offer match public offer? Pricing simplified is normal; different offer is red flag.

## Pair 4: 1d customer-voice files <-> 1b ICP signals
Real customers match inferred ICP? Mismatch flags ICP revision.

## Pair 5: 1e interview <-> all prior layers
Did interview close gaps OR contradict prior layers?

## Pair 6: MENA-fit consistency across all files
Geographic + cultural anchors consistent.

## Pair 7: Language consistency across all files
Language usage matches preference. Bilingual per-channel split honored.

## Output Format

```
| Pair | Score | Discrepancy | Resolution |
|---|---|---|---|
| ... | X/10 | ... | ... |
```

Coherence sub-score weighted 2.0x in phase composite.
