# Lasso public API documentation

This Mintlify site documents Lasso's public `/api/v1` API in English and Czech. The API implementation and primary OpenAPI definition live in the `bandits_dashboard` repository.

## Source of truth

- Sync against the `stage` branch of `bandits_dashboard` so unreleased API changes are documented before promotion.
- Start with `bandits_dashboard/api-spec/openapi.yaml`, then verify it against the handlers under `bandits_dashboard/api/v1`.
- Keep `openapi.yaml`, English endpoint pages, Czech endpoint pages, and `docs.json` navigation in sync.
- Exclude `/api/v1/internal` and dashboard-only endpoints.

The documentation OpenAPI file currently supplements the application spec with public handler routes that are not yet declared there: `GET /catalog/lookup`, `GET /catalog/changes`, `POST /tables/{table_id}/rows`, and `GET /credits/stats`.

## AI-assisted writing

Install Mintlify's documentation skill for your AI coding tools:

```bash
npx skills add https://mintlify.com/docs
```

## Local development

Install the Mintlify CLI and start the preview from the repository root:

```bash
npm i -g mint
mint dev
```

Open `http://localhost:3000`.

## Validate changes

Run these checks from the repository root:

```bash
npx mintlify@latest validate
npx mintlify@latest broken-links
npx mintlify@latest a11y
```

Before publishing an API sync, also compare the documented method/path pairs with every public handler method under `api/v1` in the Stage source tree.

## Templates and credits guides

Keep `learn/content-templates.mdx` and `learn/credits.mdx` aligned with their Czech counterparts under `cs/learn/`. The template guide covers library selection, visual and coded authoring, content sources, saved product definitions, export styling, and storefront import checks. The credits guide covers regular and one-time balances, spending order, expiry, package purchases, and public reporting semantics.

Before publishing these guides, verify package prices and purchase permissions against Stage, and distinguish coded authoring availability from existing coded content editing/export. Update related enhancement/export guides and API reference descriptions in both languages. Do not add dashboard-only purchase endpoints to the public API reference.

Validation: run `mint validate`, `mint broken-links`, and `mint a11y`, then preview the English and Czech templates and credits pages with `mint dev`. Confirm both template pages appear in navigation and preserve the existing public credit and export URLs.

Known validation debt (2026-10-05): Mint CLI 4.2.986 passes build/OpenAPI validation, links, and all 173 MDX media accessibility checks, but exits unsuccessfully for the existing theme's cross-background color contrast checks (`colors.light` against the dark background and `colors.dark` against the light background). This release does not change those colors. Owner: documentation maintainers. Exit condition: review the rendered light/dark theme and resolve the color findings or verify an upstream checker correction; retain the accessibility check in the validation workflow.
