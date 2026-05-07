# State Recovery Procedure

## Trigger

`/onboarding-guide` runs quick state validation on every invocation. Mismatch triggers recovery.

## Procedure

1. Read tracker.md → declared state
2. Scan customer folder → actual file state
3. Diff: extra files vs missing files vs score drift
4. Reconcile:
   - Extra files: log warning, update tracker, re-run skill in append mode
   - Missing files: revert tracker, suggest re-run of producing skill
   - Score drift: mark file failing, trigger gap-fill loop
5. Audit log: write `_recovery-log.md`
6. Telegram notification to operator (per ADR-001)

## Idempotency Requirement

Every skill must be safe to re-run. Inputs unchanged → outputs unchanged. Re-runs use checksum to skip unchanged work.

## Manual Recovery Commands

- `/onboarding-recovery <customer> --reset-to <sub-step>`
- `/onboarding-recovery <customer> --force-rebuild <skill>`
- `/onboarding-recovery <customer> --acknowledge-drift`
