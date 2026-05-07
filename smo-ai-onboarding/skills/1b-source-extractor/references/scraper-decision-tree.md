# Scraper Decision Tree

## Decision Logic

```
if file://: Local-mock (Read tool)
if linkedin.com: Chrome MCP (auth + JS)
if instagram/x/tiktok/facebook: Chrome MCP (anti-scraping)
if youtube/medium/substack/github: Firecrawl (clean static)
if shopify.com: Firecrawl (structured ecom)
else: Firecrawl first, Playwright fallback, Chrome MCP last resort
```

## Tools

- **Chrome MCP**: load via ToolSearch "claude-in-chrome". Auth + JS + slow.
- **Firecrawl**: via Apify actor. Fast + clean markdown + no auth.
- **Playwright**: load via ToolSearch "playwright". Complex JS + scriptable.
- **Local-mock**: Read tool for file:// URLs (test fixtures).

## Failure Handling

Log tool used, status, error, bytes. If all 3 fail: log to first-input-layer Gaps, mark unavailable, continue with other sources.
