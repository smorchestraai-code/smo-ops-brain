---
name: 3g5-deploy-whatsapp
description: "Submits WhatsApp templates to Meta via GHL, configures send flows, sets time-windows (no prayer-time/Friday violations, no 11pm Ramadan). One surface only: WhatsApp. Approval cycle is 12-72h; plan for resubmission on rejection. Use as part of /gtm-deploy."
version: 0.1.0
---

# 3g5-deploy-whatsapp

**Spec:** `phases/phase-3-gtm-strategy-brd.md` Section 10

## Purpose
Deploy assets to GHL WhatsApp via the salesmfast-ops-smo MCP. Bounded scope: this surface only.

## Inputs
- Generated assets relevant to WhatsApp
- `1-ProjectBrain/Project/` (business context)
- GHL workspace ID (from customer master Config or single-project context)

## Operations
- ghl-conversations-updater: submit templates to Meta
- ghl-conversations-reader: check approval status
- ghl-workflow-reader: link templates to flows

## Process
1. Read assets relevant to this surface.
2. Open the customer's GHL workspace (per project, multi-workspace for multi-project customers).
3. Execute MCP operations idempotently (check existing, create if missing, update if changed).
4. Smoke test: verify outputs visible in GHL UI / via reader MCP.
5. Log to `_deployment/WhatsApp.md`.

## Output
- `2-GTM/output/_deployment/whatsapp.md` per template (Meta status, template ID, send-flow config)

## Self-score
6-dim. Composite >=9.5. Smoke test must pass.

## Anti-Patterns
1. Don't deploy without dry-run check
2. Don't overwrite existing customer config silently (compare + confirm)
3. Don't skip idempotency check
4. Don't cross-deploy to sibling project's workspace (multi-project safety)

## Handoff
Next 3g skill or 3h-staged-trigger after all 3g cluster complete.
