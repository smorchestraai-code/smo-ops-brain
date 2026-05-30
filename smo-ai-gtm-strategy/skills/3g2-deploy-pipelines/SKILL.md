---
name: 3g2-deploy-pipelines
description: "Creates per-business pipelines and stages in GHL with custom fields and automation. One surface only: pipelines. Coaching pipeline = 5 stages, Wellness pipeline = 4 stages (or whatever 3a2 planned). Use as part of /gtm-deploy."
version: 0.1.0
---

# 3g2-deploy-pipelines

**Spec:** `phases/phase-3-gtm-strategy-brd.md` Section 10

## Purpose
Deploy assets to GHL Pipelines via the salesmfast-ops-smo MCP. Bounded scope: this surface only.

## Inputs
- Generated assets relevant to Pipelines
- `1-ProjectBrain/Project/` (business context)
- GHL workspace ID (from customer master Config or single-project context)

## Operations
- ghl-opportunities-updater: create pipelines with stages
- ghl-custom-field-v2-updater: stage-specific custom fields
- ghl-workflow-reader: link stages to automation triggers

## Process
1. Read assets relevant to this surface.
2. Open the customer's GHL workspace (per project, multi-workspace for multi-project customers).
3. Execute MCP operations idempotently (check existing, create if missing, update if changed).
4. Smoke test: verify outputs visible in GHL UI / via reader MCP.
5. Log to `_deployment/Pipelines.md`.

## Output
- `2-GTM/output/_deployment/pipelines.md` (pipeline structure, stages, automation)

## Self-score
6-dim. Composite >=9.5. Smoke test must pass.

## Anti-Patterns
1. Don't deploy without dry-run check
2. Don't overwrite existing customer config silently (compare + confirm)
3. Don't skip idempotency check
4. Don't cross-deploy to sibling project's workspace (multi-project safety)

## Handoff
Next 3g skill or 3h-staged-trigger after all 3g cluster complete.
