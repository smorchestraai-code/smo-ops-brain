---
name: 3g7-deploy-dashboard
description: "Builds KPI dashboard widgets in GHL: funnel rates, email open/click, pipeline movement, contact growth, WhatsApp engagement, ecom orders (if applicable). One surface only: dashboard. Use as part of /gtm-deploy as final 3g skill."
version: 0.1.0
---

# 3g7-deploy-dashboard

**Spec:** `phases/phase-3-gtm-strategy-brd.md` Section 10

## Purpose
Deploy assets to GHL Dashboard via the salesmfast-ops-smo MCP. Bounded scope: this surface only.

## Inputs
- Generated assets relevant to Dashboard
- `1-ProjectBrain/Project/` (business context)
- GHL workspace ID (from customer master Config or single-project context)

## Operations
- ghl-location-reader: workspace context for widget config
- ghl-opportunities-reader: pipeline data feeds
- ghl-email-reader: email metric feeds
- ghl-conversations-reader: WhatsApp metric feeds

## Process
1. Read assets relevant to this surface.
2. Open the customer's GHL workspace (per project, multi-workspace for multi-project customers).
3. Execute MCP operations idempotently (check existing, create if missing, update if changed).
4. Smoke test: verify outputs visible in GHL UI / via reader MCP.
5. Log to `_deployment/Dashboard.md`.

## Output
- `2-GTM/output/_deployment/dashboard.md` (widget config, KPIs tracked, refresh cadence)

## Self-score
6-dim. Composite >=9.5. Smoke test must pass.

## Anti-Patterns
1. Don't deploy without dry-run check
2. Don't overwrite existing customer config silently (compare + confirm)
3. Don't skip idempotency check
4. Don't cross-deploy to sibling project's workspace (multi-project safety)

## Handoff
Next 3g skill or 3h-staged-trigger after all 3g cluster complete.
