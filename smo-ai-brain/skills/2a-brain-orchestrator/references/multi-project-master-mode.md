# Multi-Project Altitude Model

How smo-ai-brain places brain artifacts when a customer has multiple sibling projects.

## Principle

Everything is PROJECT-level EXCEPT the 3 config files. The founder presents differently per business (persona differs), so About-Me + Project + project-instruction diverge per project. But the founder has ONE global Claude cockpit identity, so the 3 config files (profile-settings, cowork-instructions, language-preferences) live ONCE at the customer master.

## Structure (multi-project)

```
<Customer>/                       (master folder)
  _customer/
    Config/                       (3 files: profile-settings, cowork-instructions, language-preferences) <- CUSTOMER MASTER
    _customer-INDEX.md
  <Customer>-<Project1>/
    1-ProjectBrain/
      About-Me/                   (5 files, project-framed persona)        <- PROJECT
      Project/                    (~13 business files)                     <- PROJECT
      Config/project-instruction.md                                        <- PROJECT
  <Customer>-<Project2>/
    1-ProjectBrain/ ...           (own About-Me + Project + project-instruction)
```

## Altitude Rule

| Artifact | Skill | Altitude | Location |
|---|---|---|---|
| profile-settings.md | 2d | CUSTOMER | `_customer/Config/` (multi) or project Config/ (single) |
| cowork-instructions.md | 2d | CUSTOMER | `_customer/Config/` (multi) or project Config/ (single) |
| language-preferences.md | 2d | CUSTOMER | `_customer/Config/` (multi) or project Config/ (single) |
| About-Me/* (5) | 2b | PROJECT | `<project>/1-ProjectBrain/About-Me/` |
| Project/* (~13) | 2c | PROJECT | `<project>/1-ProjectBrain/Project/` |
| project-instruction.md | 2c | PROJECT | `<project>/1-ProjectBrain/Config/` |

## Single vs Multi

- Single project: customer folder = project folder. All 4 config files (3 + project-instruction) in the project Config/.
- Multi project: master folder + projects. The 3 config files hoist once to `_customer/Config/`; everything else per-project.

brain-start detects and organizes. 2f verifies: 3 config files at master (no drift), everything else project-level + no business bleed.
