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
