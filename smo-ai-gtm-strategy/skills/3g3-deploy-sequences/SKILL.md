---
name: 3g3-deploy-sequences
description: "Uploads generated email sequences to GHL as workflows. Sets triggers (form submission, tag added, opportunity stage change), schedule, sender identity. One surface only: email workflows. Use as part of /gtm-deploy after 3g2 (pipelines must exist for some triggers)."
version: 0.1.0
---

# 3g3-deploy-sequences

**Spec:** `phases/phase-3-gtm-strategy-brd.md` Section 10

## Purpose
Deploy assets to GHL Email Workflows via the salesmfast-ops-smo MCP. Bounded scope: this surface only.

## Inputs
- Generated assets relevant to Email Workflows
- `1-ProjectBrain/Project/` (business context)
- GHL workspace ID (from customer master Config or single-project context)

## Operations
- ghl-email-updater: create email templates
- ghl-workflow-reader: existing workflow check
- ghl-association-updater: link emails to workflow steps

## Process
1. Read assets relevant to this surface.
2. Open the customer's GHL workspace (per project, multi-workspace for multi-project customers).
3. Execute MCP operations idempotently (check existing, create if missing, update if changed).
4. Smoke test: verify outputs visible in GHL UI / via reader MCP.
5. Log to `_deployment/Email Workflows.md`.

## Output
- `2-GTM/output/_deployment/sequences.md` per sequence (workflow ID, trigger config)

## Self-score
6-dim. Composite >=9.5. Smoke test must pass.

## Anti-Patterns
1. Don't deploy without dry-run check
2. Don't overwrite existing customer config silently (compare + confirm)
3. Don't skip idempotency check
4. Don't cross-deploy to sibling project's workspace (multi-project safety)

## Handoff
Next 3g skill or 3h-staged-trigger after all 3g cluster complete.
