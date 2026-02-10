# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the **Yasu documentation site**, built with [Mintlify](https://mintlify.com). Yasu is an AI-powered FinOps/cloud cost optimization platform supporting AWS, Azure, and GCP.

## Development Commands

```bash
# Install Mintlify CLI (requires Node.js >= 19)
npm i -g mint

# Run local dev server (http://localhost:3000)
mint dev

# Run on custom port
mint dev --port 3333

# Update CLI to latest version
npm mint update

# Validate for broken links
mint broken-links
```

## Repository Structure

- `docs.json` — Mintlify site configuration: navigation, theme, logos, navbar, footer, and contextual options
- `index.mdx` — Landing page
- `quickstart.mdx` — Onboarding walkthrough (account creation, cloud connection, agents, team invite)
- `development.mdx` — Local dev setup instructions (part of the docs content itself)
- `guides/` — Cloud provider connection guides (connect-aws, connect-gcp, connect-azure, plus Azure billing type variants: mca, ea, csp)
- `api-reference/` — API endpoint docs + `openapi.json` spec
- `ai-tools/` — Integration guides for Claude Code, Cursor, Windsurf
- `snippets/` — Reusable MDX content fragments (imported via `<Snippet />`)
- `images/` — Screenshots organized by feature area (onboarding/, aws/, ui/)
- `logo/` — Light/dark SVG logos

## Content Conventions

- All content pages use `.mdx` format with YAML frontmatter (`title`, `description`, optional `icon`)
- Pages use Mintlify components: `<Steps>`, `<Tabs>`, `<Card>`, `<CardGroup>`, `<Columns>`, `<Info>`, `<Warning>`, `<Tip>`, `<Note>`, `<Check>`, `<Accordion>`, `<AccordionGroup>`, `<Frame>`
- Navigation structure is defined entirely in `docs.json` under `navigation.tabs[].groups[].pages` — new pages must be added here to appear in the sidebar
- Images are referenced with relative paths from the doc root (e.g., `images/onboarding/connect_aws.jpg`)

## Deployment

Pushes to the `main` branch automatically deploy to production via the Mintlify GitHub app.
