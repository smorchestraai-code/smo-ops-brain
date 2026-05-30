# 3 Telegram Gates (detailed spec)

## Gate 1: Asset Pack Approval (after 3f scoring)

**Trigger conditions:**
- All assets scored >=9.5 (3f)
- All 8 coherence pairs >=9.0 (3f1)
- Zero fabrications, INPUT-GAPs <=5% (3f2)

**Shown to operator (Telegram message):**
```
Phase 3 Asset Pack Ready for Approval
Customer: <name> / Project: <project>
Playbook: <id> (primary), <id> (secondary)

Assets:
  Sequences: N (avg score X.X)
  Funnels:   N (avg score X.X)
  WhatsApp:  N (avg score X.X)
  Content:   N (avg score X.X)

Voice-fit: X.X/10
Traceability: 100% (or X% with N INPUT-GAPs)
Coherence pairs: 8/8 passing

INPUT-GAPs to surface to founder:
  - <element>: <reason>
  - <element>: <reason>

Reply: APPROVE | EDIT | REJECT
```

**Default if no response in 48h:** Hold, ping ops lead.

## Gate 2: Trigger Approval (after 3g deployment + smoke test)

**Trigger conditions:**
- All 7 GHL surfaces deployed (3g cluster)
- Smoke test passed (1 test contact, 3h Stage 0)
- Gate 1 already cleared

**Shown to operator:**
```
Phase 3 Trigger Approval Ready
Customer: <name> / Project: <project>

Deployment:
  Contacts: N imported, M tagged
  Pipelines: live, K stages
  Sequences: N workflows live
  Funnels: N pages published, URLs: ...
  WhatsApp: M templates submitted to Meta (status: ...)
  Calendar: booking URL live
  Dashboard: live

Smoke test: PASSED
  Test contact: <email>
  Rendering: OK / Links: OK / Personalization: OK

First-send preview:
  Subject: "..."
  First 3 lines: "..."

Segment sizes:
  Welcome sequence: 2,400 contacts
  Wellness post-purchase: 850 contacts
  ...

Reply: TRIGGER | STAGE 10% | PAUSE | REJECT
```

**Default after 72h:** Auto-pause.

## Gate 3: Scale Approval (48h after full-batch trigger)

**Trigger conditions:**
- Full batch sent
- 48h observation window complete
- Outcome metrics captured

**Shown to operator:**
```
Phase 3 Scale Approval Ready
Customer: <name> / Project: <project>

Outcome (48h post-trigger):
  Open rate: X% (industry benchmark: Y%, MENA Pro Services: Z%)
  Reply rate: X% (benchmark: Y%)
  Conversion: X (if measurable)
  Bounces: X% (threshold: 2%)
  Spam reports: N (threshold: 0)

Trend: ABOVE / AT / BELOW benchmark

Recommendation: EXPAND | HOLD | MODIFY
  Reasoning: ...

Reply: EXPAND | HOLD | MODIFY
```

**Default:** Hold (conservative).

## Escalation paths

- Gate 1 stalled >48h: ops lead
- Gate 2 stalled >72h: customer
- Gate 3 stalled >72h: customer + ops lead
- Smoke test failed: ops lead + tech
- Stage 1 thresholds breached: ops lead + auto-pause
