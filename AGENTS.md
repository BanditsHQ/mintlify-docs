> For Mintlify product knowledge (components, configuration, writing standards),
> install the Mintlify skill: `npx skills add https://mintlify.com/docs`

# Documentation project instructions

## About this project

- This is a documentation site built on [Mintlify](https://mintlify.com)
- It documents Lasso's public API implemented in the sibling `bandits_dashboard` repository
- The `bandits_dashboard` `stage` branch is the release-candidate source of truth
- Pages are MDX files with YAML frontmatter
- API operations are rendered from the root `openapi.yaml`
- Configuration lives in `docs.json`
- Run `mint dev` to preview locally
- Run `mint broken-links` to check links

## Terminology

- Use **Lasso** for the product and **Catalog** for its product catalog.
- Capitalize **Attribute** when referring to the reusable company Attribute dictionary.
- Use **Product Schema** for a reusable extraction schema and **table** for an extraction job.
- Write endpoint paths relative to the documented base URL, for example `GET /tables/{table_id}`.
- Use handler parameter names such as `table_id`, `row_id`, and `schema_id` instead of generic `{id}` placeholders.

## Style preferences

{/* Add any project-specific style rules below */}

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references

## Content boundaries

- Document public `/api/v1` handlers only. Never publish `/api/v1/internal` or dashboard-only endpoints.
- Keep hosted systems read-only while researching documentation changes.
- Verify the application OpenAPI file against actual Stage handlers. Handler behavior wins when they differ.
- Keep English and Czech API navigation and operation coverage identical.
- Preserve existing public documentation URLs when updating generated API pages.
