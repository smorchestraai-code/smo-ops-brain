# Gap Detection Logic

## Coverage Matrix
10 brain dimensions x N signal sources (1b sources + 1c memory + 1d files).

Per dim x source: confidence (0-10).
Coverage(dim) = max OR weighted avg of top-3 confidence scores.

## Question Selection

Per dim where coverage <9.0:
1. Identify weak sub-fields
2. Load template from `_templates/Interview-Questions/<dim>.template.md`
3. Pick 1-3 questions targeting weak sub-fields
4. Customize with already-known signals

Max 25 questions total (cognitive fatigue cap = 2 hours founder time).

## Always Include

- 12-question tools inventory (Phase 5 plugin-creator needs full stack)
- Conflict resolution questions for any 1b coherence pair <8.0

## Output Format

```
## <Dimension> (coverage: X/10)
- Q1.1: <specific question>
- Q1.2: ...
```

Show coverage. Skip dims ≥9.0 with explicit annotation (transparency).
