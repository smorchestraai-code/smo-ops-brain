---
name: 3a-gtm-orchestrator
description: "Reads a locked Phase 2 brain, detects persona + complexity signals, builds the asset-source-map that maps every asset element to its brain field, and produces the _build-plan.md that drives the rest of Phase 3. First skill in Phase 3. Use when user runs /gtm-build, /gtm-plan, or as part of /gtm-start chain. Enforces zero-hallucination by requiring downstream generators to cite a brain source for every asset element."
version: 0.1.0
---

# 3a-gtm-orchestrator

## Purpose
Plan the full Phase 3 build. Build the anti-hallucination spine.

## Preconditions
Phase 2 locked. If not: exit with instructions.

## Inputs
- `1-ProjectBrain/About-Me/`, `Project/`, `Config/`
- `0-Input/persona-and-priority.md`
- `_customer/Config/` if multi-project

## Process
1. Read all brain inputs.
2. Detect complexity: multi-product? multi-pipeline? content-heavy? bilingual? heavy WhatsApp?
3. Hand off to 3a1 to pick 1 primary + 1 secondary playbook.
4. Hand off to 3a2 for adaptive asset counts.
5. Build `_asset-source-map.md`: per asset element -> brain field(s). No source -> INPUT-GAP.
6. Write `_build-plan.md`: playbook + asset list + reasoning + INPUT-GAP summary.

## Output
- `2-GTM/output/_build-plan.md`
- `2-GTM/output/_asset-source-map.md`
- `2-GTM/output/_input-gaps.md` (if any)

## Self-score
6-dim incl. traceability. Source-map covers every planned asset element. Composite >=9.5.

## Anti-Patterns
1. Don't plan a field with no brain source (mark INPUT-GAP)
2. Don't hardcode counts
3. Don't skip the source-map

## Handoff
3a1-playbook-selector, 3a2-asset-list-planner
