# BaseMouse Cursor plugin

Cursor / Grok Bot plugin wrapping BaseMouse MCP.

- MCP: `https://basemouse.com/mcp`
- Tools: `search`, `get_context_pack`, `upsert_document`
- Identifier: `basemouse` (kebab-case `name` in `.cursor-plugin/plugin.json`)
- Numeric marketplace id is assigned after Cursor review, not in this repo

## Auth

Marketplace / one-click install is URL-only. Cursor starts OAuth against `https://basemouse.com/mcp`. Paste your existing `bm_...` key on the BaseMouse consent page (or continue with the public demo).

Config-file clients can still send `Authorization: Bearer bm_...` themselves. The optional `BASEMOUSE_API_KEY` plugin variable is for that path, not for marketplace Connect. Never commit a key.

## Local test

```bash
mkdir -p ~/.cursor/plugins/local/basemouse
# copy this repo contents into that folder, including .cursor-plugin/plugin.json
```

Reload Window. Confirm the BaseMouse MCP tools load. Connect should prompt OAuth, not ask you to paste a key into plugin config.

## Publish

Public repo. Submit at https://cursor.com/marketplace/publish

Layout follows https://github.com/cursor/plugin-template as a single plugin at repo root (no `marketplace.json`).

Docs: https://cursor.com/docs/plugins and https://cursor.com/docs/reference/plugins
Product: https://basemouse.com  Source: https://github.com/basemouse/basemouse-core
