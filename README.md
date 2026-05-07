# SMO Ops Brain Marketplace

SMOrchestra.ai's plugin marketplace for AI-Native Customer Operations.

This marketplace contains plugins that power SMO's customer onboarding system, GTM operations, and ongoing optimization service.

## Plugins

| Plugin | Status | Description |
|---|---|---|
| `smo-ai-onboarding` | v0.5.0 (Phase 1 built) | Customer onboarding: input capture, brain context, GTM strategy, plugin BRDs |
| `smo-ai-plugin-creator` | Planned | Consumes BRDs, generates customer-specific plugin instances |
| `smo-ai-cockpit` | Planned | Universal cockpit: smo-guide + macro-scorer + outcome-scorer + tracker |

## Installing the Marketplace

In Claude Cowork, run:

```
/plugin marketplace add smorchestraai-code/smo-ops-brain
```

Then install plugins:

```
/plugin install smo-ai-onboarding@smo-ops-brain
```

## For SMO Team

Clone this repo to keep local copy in sync:

```bash
git clone https://github.com/smorchestraai-code/smo-ops-brain.git
cd smo-ops-brain
```

Pull updates:

```bash
git pull origin main
```

## Repository Structure

```
smo-ops-brain/
├── .claude-plugin/
│   └── marketplace.json
├── smo-ai-onboarding/
│   ├── .claude-plugin/plugin.json
│   ├── commands/
│   ├── skills/
│   ├── phases/
│   ├── recovery/
│   ├── tests/fixtures/Acme-MENATech/
│   └── README.md
├── README.md
└── INSTALL.md
```

## Versioning

Each plugin has its own version in its `plugin.json`. Marketplace version reflects marketplace metadata, not individual plugin versions.

## Support

- Owner: Mamoun Alamouri (smorchestra.ai@gmail.com)
- Issues: open in this repo

## License

Proprietary. Internal use by SMOrchestra.ai team and authorized customers.
