# Multi-Project Master Mode

How smo-ai-brain handles a customer with multiple sibling projects.

## Structure

```
<Customer>/                       (master folder = customer name)
  _customer/                      (META layer - written ONCE, transcends projects)
    About-Me/                     (5 founder files, from 2b)
    Config/                       (profile-settings, cowork-instructions, language-preferences, from 2d)
  <Customer>-<Project1>/          (full project structure)
    1-ProjectBrain/
      Project/                    (business files, from 2c)
      Config/project-instruction.md  (project-level, from 2d)
  <Customer>-<Project2>/
    1-ProjectBrain/ ...
```

## Altitude Rule

| Artifact | Skill | Altitude | Location |
|---|---|---|---|
| About-Me/* | 2b | CUSTOMER | `_customer/About-Me/` |
| profile-settings.md | 2d | CUSTOMER | `_customer/Config/` |
| cowork-instructions.md | 2d | CUSTOMER | `_customer/Config/` |
| language-preferences.md | 2d | CUSTOMER | `_customer/Config/` |
| project-instruction.md | 2d | PROJECT | `<project>/1-ProjectBrain/Config/` |
| Project/* | 2c | PROJECT | `<project>/1-ProjectBrain/Project/` |

## Detection

Multi-project mode when persona-and-priority.md has `multi-project: yes` AND names a sibling, OR the project folder sits inside a `<Customer>/` master alongside siblings.

## Single-project mode

No `_customer/` layer. About-Me + all Config in the project's own 1-ProjectBrain/.

## Consolidation step (the additional step for multi-project)

After project brains built, 2f master assembly check:
1. About-Me once to `_customer/About-Me/`
2. Meta-config once to `_customer/Config/`
3. No drift (founder facts identical across runs)
4. No business bleed (project-scoped)
5. project-instruction per project

## Build order

1. /brain-build Project1 -> About-Me + meta-Config hoisted to `_customer/` + Project1 files + Project1 project-instruction
2. /brain-build Project2 -> meta already at `_customer/` (verify no drift) + Project2 files + Project2 project-instruction
3. 2f master assembly check across both
