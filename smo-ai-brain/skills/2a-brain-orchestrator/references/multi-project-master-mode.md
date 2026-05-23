# Multi-Project Organization (no shared brain)

How smo-ai-brain handles a customer with multiple sibling projects.

## Principle

Each project brain is SELF-CONTAINED. There is NO shared customer brain layer. The founder presents differently per business (persona differs), so About-Me + Config diverge per project. The master folder is purely organizational.

## Structure

```
<Customer>/                       (master folder = organizational container only)
  _customer/_customer-INDEX.md    (project roster, no brain)
  <Customer>-<Project1>/
    1-ProjectBrain/
      About-Me/                   (5 files, project-framed persona)
      Project/                    (~13 business files)
      Config/                     (profile-settings, cowork-instructions, language-preferences, project-instruction)
  <Customer>-<Project2>/
    1-ProjectBrain/ ...           (fully independent brain)
```

## Altitude Rule (everything project-level)

| Artifact | Skill | Location |
|---|---|---|
| About-Me/* (5) | 2b | `<project>/1-ProjectBrain/About-Me/` |
| Project/* (~13) | 2c | `<project>/1-ProjectBrain/Project/` |
| project-instruction.md | 2c | `<project>/1-ProjectBrain/Config/` |
| profile-settings, cowork-instructions, language-preferences | 2d | `<project>/1-ProjectBrain/Config/` |

## Single vs Multi

- Single project: customer folder = project folder (flat).
- Multi project: master folder + project subfolders, each self-contained.

brain-start detects and organizes. No de-dup, no hoisting, no drift checks across siblings (nothing is shared). The only cross-project check 2f runs is no-business-bleed within each project.
