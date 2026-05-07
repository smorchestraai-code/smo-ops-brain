---
description: "Start customer onboarding. Runs Phase 1 mini-intake."
---

# /onboarding-start

Canonical entry point. Start customer onboarding.

## Usage

```
/onboarding-start <customer-folder-name>
```

If the folder exists in clients-onboarding/, the command resumes intake. If new, scaffold gets instantiated from `_state-0-customer-scaffold/`.

## What this command does

1. Verifies customer folder exists OR creates from state-0 scaffold
2. Invokes `1a-mini-intake` skill
3. Suggests next action (typically /onboarding-guide for the rest of Phase 1)

## Output

- Customer folder ready at `clients-onboarding/<customer-folder-name>/`
- `0-Input/persona-and-priority.md` populated
- `tracker.md` shows Phase 0a in-progress

## Next

After /onboarding-start completes, run /onboarding-guide.
