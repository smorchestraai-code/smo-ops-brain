# Scaffold Instantiation Logic

## Decision Tree

1. Customer folder exists? NO -> copy state-0 scaffold. YES -> check persona-and-priority.md status.
2. If multi-project: per-project folder, About-Me copied (Pattern A).
3. After scaffold ready: write persona-and-priority.md, init tracker, update progress.

## Multi-Project About-Me Sharing

Pattern A (default): duplicate copies per project. Sync via Phase 2 brain-orchestrator.
Pattern B (Mac/Linux only): symlinks. Skipped due to Windows incompatibility.

## Anti-Patterns

- Never delete existing customer folder
- Never overwrite populated 0-Input/persona-and-priority.md without confirmation
- Never auto-create multi-project without explicit Q2=multi answer
- Never use customer name with spaces in folder name

## Verification

After instantiation: test folder exists, 0-Input/ exists, persona-and-priority.md exists, tracker.md exists.
