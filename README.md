# BaseMouse Cursor plugin

Cursor / Grok Bot plugin wrapping BaseMouse MCP.

- MCP: `https://basemouse.com/mcp`
- Tools: `search`, `get_context_pack`, `upsert_document`
- Identifier: `basemouse` (kebab-case `name` in `.cursor-plugin/plugin.json`)
- Numeric marketplace id is assigned after Cursor review, not in this repo

## Configure

Set `BASEMOUSE_API_KEY` in Cursor dashboard, Plugins, Configure. Leave it empty for the public demo corpus. Never commit a key.

## Local test

```bash
mkdir -p ~/.cursor/plugins/local/basemouse
# copy this repo contents into that folder, including .cursor-plugin/plugin.json
```

Reload Window. Confirm the BaseMouse MCP tools load.

## Publish

Public repo. Submit at https://cursor.com/marketplace/publish

Layout follows https://github.com/cursor/plugin-template as a single plugin at repo root (no `marketplace.json`).

Docs: https://cursor.com/docs/plugins and https://cursor.com/docs/reference/plugins
Product: https://basemouse.com  Source: https://github.com/basemouse/basemouse-core
