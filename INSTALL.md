# Installing SMO Ops Brain Plugins

## Prerequisites

- Claude Cowork (desktop app)
- GitHub access to SMOrchestra-ai org (for private repo access)

## Method 1: Install via Cowork Marketplace UI

1. Open Claude Cowork
2. Run `/plugin marketplace add SMOrchestra-ai/smo-ops-brain`
3. Cowork will fetch the marketplace
4. Run `/plugin install smo-ai-onboarding@smo-ops-brain`
5. Confirm installation
6. Plugin commands now available: `/onboarding-start`, `/onboarding-guide`, etc.

## Method 2: Install from .plugin file (offline)

1. Clone or download this repo
2. Each plugin folder can be zipped: `cd plugin-name && zip -r /tmp/plugin-name.plugin . -x "*.DS_Store"`
3. Drag the `.plugin` file into Cowork chat
4. Click Install in the rich preview

## Method 3: Local development

For local plugin development without GitHub:

```bash
git clone https://github.com/SMOrchestra-ai/smo-ops-brain.git
cd smo-ops-brain/smo-ai-onboarding
# Edit files
# Test locally via Cowork .local-plugins folder
```

## Updating

When marketplace updates:

```
/plugin marketplace update smo-ops-brain
/plugin update smo-ai-onboarding@smo-ops-brain
```

Or via git for local clones:

```bash
cd smo-ops-brain
git pull origin main
```

## Team Sync

For SMO team:

1. Add this repo as a Cowork marketplace once (Method 1)
2. Pull updates weekly OR set up auto-update (per Cowork preference)
3. Optimization service syncs customer instances based on macro-scorer + outcome-scorer findings

## Troubleshooting

- "Plugin validation failed": ensure you cloned the repo cleanly, no extra files at plugin root
- "Cannot find marketplace.json": verify `.claude-plugin/marketplace.json` exists at repo root
- "Permission denied to repo": contact mamoun@smorchestra.ai for GitHub org access
