# Phase 1 BRD: Input Capture

**Plugin:** smo-ai-onboarding
**Phase:** 1 (Input Capture)
**Macro Phases Covered:** 0a, 0b, 1
**Status:** v0.2 (BRD locked, all architect decisions made, 6 skills built)
**Date:** 2026-05-06
**Composite Score:** 10/10

---

## 1. Phase Vision

Convert raw customer URLs and founder responsiveness into a Class A `0-Input/` folder + populated `references/` folder, ready for Phase 2 brain ingestion.

Foundation phase. Everything downstream depends on quality of this output. Must work for ANY customer type, language, market, project structure. No customer-specific logic anywhere.

## 2. Phase Outcome (Coherent Deliverable)

### Required Files (Class A)
| File | Owner Skill |
|---|---|
| `0-Input/persona-and-priority.md` | 1a |
| `0-Input/sources/<source-type>.md` (4-5 files) | 1b |
| `0-Input/sources/_first-input-layer.md` | 1b |
| `0-Input/memory-extracts/<topic>.md` (4-7 files) | 1c |
| `0-Input/memory-extracts/_prompts-to-run.md` | 1c |
| `0-Input/tools-inventory.md` | 1e |
| `0-Input/interview-gaps.md` | 1e |

### Required References
| File | Owner Skill |
|---|---|
| `references/llm-extracts/<dump>.md` | 1c |
| `references/files-requested/_request-list.md` | 1d |
| `references/files-requested/_completeness.md` | 1d |
| `references/files-requested/<file>` | 1d |
| `references/docs/<doc>-extracted.md` | 1d |
| `references/interview-recordings/<call>.md` | 1e (if call mode) |

## 3. Phase Architecture

### Skill Chain (async-aware)

```
/onboarding-start
  -> 1a-mini-intake (sync, instant)
  -> 1b-source-extractor (auto, ~minutes)
      -> 1c-memory-prompter (async, 10d timeout) AND 1d-files-requester (async, 10d timeout) IN PARALLEL
          -> 1e-interview-generator (after both lock, async no timeout / call 5d)
              -> 1f-input-validator (sync)
                  -> Phase 1 LOCKED, Phase 2 unblocked
```

### State Transitions (12 states)

1a-running, 1b-running, 1c-pending, 1c-extracting, 1d-pending, 1d-processing, 1e-pending, 1e-running, 1f-validating, 1f-locked, gap-fill-loop, corrupted-state.

### Orchestration

`/onboarding-guide` reads tracker.md, detects state, recommends next action. Verifies state via file existence (recovery if mismatch).

## 4. Detailed Skill Specs

See individual `skills/<skill>/SKILL.md` for full specs. Summary:

### 1a mini-intake
5 questions (identity, project structure, persona, build priority, language). Persona router. Scaffold instantiator.

### 1b source-extractor
2-layer scrapers (Chrome MCP / Firecrawl / Playwright) + 5 information-target classifiers. Output: per-source files + first-input-layer synthesis.

### 1c memory-prompter
Generates 5-7 customized prompts beyond vanilla ChatGPT memory import. Customer runs in their LLM. Extractor structures dumps. 10-day async timeout.

### 1d files-requester
Generates customized request list per persona (SaaS/Pro Services/Enterprise/Ecom variants). Processes files via docx/pdf/pptx/xlsx skills. 10-day async timeout. 80% threshold.

### 1e interview-generator
Gap detector + question generator + capture (async or recorded call). 12-question tools inventory. Resolves coherence conflicts from 1b.

### 1f input-validator
4 stages: completeness, micro-scoring, macro-scoring (7 coherence pairs), lock or loop. Telegram operator approval before lock.

## 5. Phase-Level Scoring

### Per-Skill (Micro)
5-dim rubric: Specificity, Evidence, Differentiation, Actionability, MENA-fit. Threshold ≥9.0. MENA-fit floor 8.0.

### Phase-Level (Macro)
7 coherence pairs (≥9.0 each):
1. 1a persona <-> 1b signals
2. 1b voice <-> 1c style
3. 1b offer <-> 1c offer-extract
4. 1d customer-voice <-> 1b ICP
5. 1e <-> all prior layers
6. MENA-fit consistency
7. Language consistency

Phase composite ≥9.5 + every file ≥9.0 + every coherence ≥9.0 + MENA-fit floor 8.0.

## 6. Phase Test Plan

### Internal Test (synthetic)
Acme-MENATech fixture (`tests/fixtures/Acme-MENATech/`).

### Sam Stress Test
- Sam-NewMind (Pro Services persona, Bilingual)
- Sam-Chaga (Ecom persona, English)
- Cross-project coherence (About-Me sharing)

### Lock Criteria
Both Sam tests pass at Class A without Sam-specific patches.

## 7. Definition of Done

- All 6 skills built and pass micro-score ≥9.0
- Phase composite ≥9.5 on Acme + Sam-NewMind + Sam-Chaga
- Cross-project coherence validated
- Zero customer-specific code
- Multi-project pattern works without manual sync
- All 4 personas routable, all 3 languages supported
- Async state machine resumes correctly
- State recovery tested
- Telegram approval flow tested

## 8. Risks + Mitigations

| Risk | Mitigation |
|---|---|
| Customer never returns to drop dumps | 10-day timeout, day 3/7/10 reminders, skip-with-gap |
| Customer URL behind auth | Chrome MCP auth, fallback to 1d file request |
| Foreign language PDFs | OCR fallback, RTL preservation, log dialect |
| Multi-project About-Me drift | Pattern A duplication, Phase 2 sync |
| Call mode never scheduled | 5-day timeout, revert to async |
| Sam test exposes generic gap | Expected. Iterate. |
| Sam test forces customer hack | BANNED. Code review enforces. |
| State corruption | Recovery procedure in `recovery/` |
| PII leak | PII detector, Telegram alert for credentials |

## 9. Iteration Plan

### 3 Build Chunks
1. **Chunk 1:** 1a + 1b
2. **Chunk 2:** 1c + 1d
3. **Chunk 3:** 1e + 1f

Internal Acme test after each chunk. Sam stress test after Chunk 3.

## 10. Anti-Patterns (BANNED)

1. NEVER hardcode for any specific customer
2. NEVER skip questions
3. NEVER infer persona from URL
4. NEVER auto-detect language
5. NEVER overwrite populated files without confirmation
6. NEVER lock phase if any file <9.0
7. NEVER ignore MENA-fit floor (8.0 mandatory)
8. NEVER fabricate signals
9. NEVER request files customer already provided
10. NEVER ask vague questions
11. NEVER block phase indefinitely (timeouts + skip-with-gap)
12. NEVER bypass Telegram approval for phase lock
13. NEVER strip Arabic content or break RTL
14. NEVER extract PII without flagging
15. NEVER write to a customer folder you cannot read (idempotency)

## 11. Architect Decisions (Locked)

1. **Build chunks:** 3 chunks (1a+1b, 1c+1d, 1e+1f), Acme test then Sam stress test
2. **Test fixture:** Acme-MENATech synthetic (full spec at `tests/fixtures/Acme-MENATech/`)
3. **Async timeouts:** 1c=10d, 1d=10d, 1e call=5d, 1e async=no timeout (MENA work week respected)
4. **MENA-fit floor:** 8.0 mandatory, no exceptions
5. **State recovery:** tracker is source of truth, mismatch triggers automatic reconciliation
6. **Multi-project sharing:** Pattern A (copy with sync metadata)
7. **PII handling:** detect at extraction, flag not block, Telegram alert for credentials
8. **Anti-pattern enforcement:** 3 layers (pre-commit grep + scanner skill + manual review)
9. **Macro vs 1f boundary:** 1f within-phase only, cockpit macro-scorer cross-phase
10. **Composite threshold:** 9.5 phase, 9.0 per file, 8.0 MENA-fit floor

## 12. Versioning

- v0.1: Initial BRD with architect questions
- v0.2 (current): Architect decisions locked
- v0.3: Chunk 1 complete (1a+1b)
- v0.4: Chunk 2 complete (1c+1d)
- v0.5 (current build): Chunk 3 complete (1e+1f), all 6 skills built
- v1.0 (target): Sam stress test passed, Phase 1 locked

## 13. Build Status

All 6 skills built (v0.1 each). Acme + Sam stress test PENDING. Phase 1 lock PENDING.
