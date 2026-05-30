---
name: 3g1-deploy-contacts
description: "Deploys customer contacts (CSV from references/raw-uploads-2026-05-11/) into GHL: imports, dedupes, tags by source segment, assigns to workflows. One surface only: contacts. Use as part of /gtm-deploy after 3f scoring passes Gate 1 (pack approval)."
version: 0.1.0
---

# 3g1-deploy-contacts

**Spec:** `phases/phase-3-gtm-strategy-brd.md` Section 10

## Purpose
Deploy assets to GHL Contacts via the salesmfast-ops-smo MCP. Bounded scope: this surface only.

## Inputs
- Generated assets relevant to Contacts
- `1-ProjectBrain/Project/` (business context)
- GHL workspace ID (from customer master Config or single-project context)

## Operations
- ghl-contacts-updater: create/update contacts in bulk
- ghl-contacts-reader: dedup check, existing contact lookup
- ghl-custom-field-v2-updater: ensure required custom fields exist
- ghl-workflow-reader: get workflow IDs for assignment

## Process
1. Read assets relevant to this surface.
2. Open the customer's GHL workspace (per project, multi-workspace for multi-project customers).
3. Execute MCP operations idempotently (check existing, create if missing, update if changed).
4. Smoke test: verify outputs visible in GHL UI / via reader MCP.
5. Log to `_deployment/Contacts.md`.

## Output
- `2-GTM/output/_deployment/contacts.md` (count imported, deduped, tagged, assigned)

## Self-score
6-dim. Composite >=9.5. Smoke test must pass.

## Anti-Patterns
1. Don't deploy without dry-run check
2. Don't overwrite existing customer config silently (compare + confirm)
3. Don't skip idempotency check
4. Don't cross-deploy to sibling project's workspace (multi-project safety)

## Handoff
Next 3g skill or 3h-staged-trigger after all 3g cluster complete.
