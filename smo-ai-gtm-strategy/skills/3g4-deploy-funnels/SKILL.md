---
name: 3g4-deploy-funnels
description: "Builds funnel pages in GHL (opt-in, sales, thank-you), sets domain/subdomain, configures tracking, publishes. One surface only: funnels. Auto-tagging logic wired per planned funnel. Use as part of /gtm-deploy."
version: 0.1.0
---

# 3g4-deploy-funnels

**Spec:** `phases/phase-3-gtm-strategy-brd.md` Section 10

## Purpose
Deploy assets to GHL Funnels + Pages via the salesmfast-ops-smo MCP. Bounded scope: this surface only.

## Inputs
- Generated assets relevant to Funnels + Pages
- `1-ProjectBrain/Project/` (business context)
- GHL workspace ID (from customer master Config or single-project context)

## Operations
- ghl-blog-updater: pages content (GHL funnels API)
- ghl-media-updater: hero images, asset uploads
- ghl-custom-field-v2-updater: form fields per funnel
- ghl-association-updater: tag-on-submit rules

## Process
1. Read assets relevant to this surface.
2. Open the customer's GHL workspace (per project, multi-workspace for multi-project customers).
3. Execute MCP operations idempotently (check existing, create if missing, update if changed).
4. Smoke test: verify outputs visible in GHL UI / via reader MCP.
5. Log to `_deployment/Funnels + Pages.md`.

## Output
- `2-GTM/output/_deployment/funnels.md` per funnel (URL, page IDs, tracking config)

## Self-score
6-dim. Composite >=9.5. Smoke test must pass.

## Anti-Patterns
1. Don't deploy without dry-run check
2. Don't overwrite existing customer config silently (compare + confirm)
3. Don't skip idempotency check
4. Don't cross-deploy to sibling project's workspace (multi-project safety)

## Handoff
Next 3g skill or 3h-staged-trigger after all 3g cluster complete.
