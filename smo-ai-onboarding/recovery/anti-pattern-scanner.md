# Anti-Pattern Scanner

Scans plugin folder for customer-specific code. Runs pre-commit, after every change, before lock.

## Patterns BANNED

### Hardcoded customer names
```regex
\b(Sam|Layla|Ahmed|Mohammed|NewMind|Acme-MENATech|GulfRetail)\b
```
Exception: tests/fixtures/ + BRD examples.

### Hardcoded URLs
```regex
\b(samdaghash\.com|newmind\.ae|acme-menatech\.example)\b
```
Exception: tests/fixtures/ + BRD examples.

### Persona-specific logic outside variants
```regex
if\s+persona\s*==\s*['"]?\w+['"]?\s*:
```
Allowed: `_templates/<area>/<persona>.md` variants and persona router.
Banned: 1b classifiers, 1c prompt generation, 1f validation.

### Customer-specific paths
```regex
clients-onboarding/(Sam-|Acme-|NewMind-)
```
Exception: test fixtures, customer documentation.

## Severity

- Critical: hardcoded customer name/URL in skill (not test fixture). Block lock.
- High: persona logic outside variant. Block lock.
- Medium: scoring deviation, hardcoded path in test runner. Warning.

## Pass: zero critical + zero high.

## Implementation

Read all `.md` files recursive. Apply regex. Filter exceptions. Output report. Telegram alert on critical/high. Block lock.
