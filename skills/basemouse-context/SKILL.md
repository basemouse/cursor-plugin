---
name: basemouse-context
description: Use when you need grounded project docs, citations, or durable memory across agent tools. Pull a BaseMouse context pack, cite checksums, upsert decisions by stable id.
---

# BaseMouse context

MCP tools: `search`, `get_context_pack`, `upsert_document`. Endpoint is `https://basemouse.com/mcp`. Auth is `Authorization: Bearer bm_...` via plugin variable `BASEMOUSE_API_KEY`. No key means public demo corpus only.

## Read

1. Call `get_context_pack` with `q` (and optional `limit`, `type`, `tag`). `tag=project:<slug>` scopes one project.
2. Treat entries as grounded. Do not invent facts past the pack.
3. Cite `citation.label` or `id`. Prefer higher `relevance.score`, then newer `provenance.updatedAt`.
4. If `truncated` is true, raise `limit` or refine `q`.
5. Follow `related` / `relationships` for the next retrieve.

## Write

`upsert_document` by stable `id`. Unchanged body writes nothing. Real changes append a revision. Use this so another client can `get_context_pack` the same decision.

## Do not

Do not put API keys in files. Do not claim semantic embeddings; hybrid retrieval is lexical + one-hop graph + local hashed vectors.
