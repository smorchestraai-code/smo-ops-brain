# smo-ai-gtm-strategy (Plugin)

Phase 3 of the SMO-AI customer journey. Converts a locked Phase 2 brain into a deployed, triggered GTM motion at Class A.

**Version:** 0.1.0
**Consumes:** Locked `1-ProjectBrain/` (from smo-ai-brain Phase 2)
**Produces:** Deployed + triggered GTM motion (assets in `2-GTM/output/` + live campaigns in GHL via SalesMfast)

## Chain

```
brain
  -> playbook (1 of 13)
    -> adaptive asset list (per persona + complexity)
      -> assets generated with voice-in-context (zero hallucination)
        -> scored (type-specific rubrics + traceability + 8 coherence pairs)
          -> deployed to GHL across 7 surfaces
            -> staged trigger (test contact -> small batch -> full)
              -> Phase 3 locked, handoff to Phase 4
```

## Skills (19)

Planning (3 skills):
- `3a-gtm-orchestrator` - read brain, build `_asset-source-map.md`, plan
- `3a1-playbook-selector` - recommend 1 of 13 playbooks
- `3a2-asset-list-planner` - adaptive counts driven by persona + complexity

Generation (4 skills, voice-in-context):
- `3b-sequence-builder`, `3c-funnel-builder`, `3d-whatsapp-builder`, `3e-content-builder`

Scoring (3 skills):
- `3f-asset-scorer`, `3f1-coherence-validator`, `3f2-traceability-validator`

Deployment (7 skills, per GHL surface):
- `3g1-deploy-contacts`, `3g2-deploy-pipelines`, `3g3-deploy-sequences`, `3g4-deploy-funnels`, `3g5-deploy-whatsapp`, `3g6-deploy-calendar`, `3g7-deploy-dashboard`

Trigger + Validate (2 skills):
- `3h-staged-trigger`, `3i-gtm-validator`

## Commands

Standard quartet: `gtm-start`, `gtm-guide`, `gtm-status`, `gtm-validate`.
Manual: `gtm-build`, `gtm-plan`, `gtm-generate`, `gtm-score`, `gtm-deploy`, `gtm-trigger`.
Canonical: `/gtm-start`.

## Altitude

Everything project-level. Each project gets its own GTM motion. Multi-business: run `gtm-build` sequentially per project.

## Zero hallucination

Every asset element cites the brain field that drove it. `3a` builds `_asset-source-map.md`. Generators cite per element. `3f2` verifies. INPUT-GAPs marked honestly, never invented.

## Voice-in-context

Generators load brand-voice + communication-style + founder voice samples as PRIMARY context. Voice conformance built in at generation, not post-hoc.

## 3 Telegram gates (per ADR-001)

Pack approval, Trigger approval, Scale approval. Staged rollout inside Gate 2: test contact -> small batch (10% or 50) -> full batch.

Full spec: `phases/phase-3-gtm-strategy-brd.md`.
