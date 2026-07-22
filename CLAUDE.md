# mcp_excalidraw (external source)

Third-party repo (github: yctimlin/mcp_excalidraw) providing an Excalidraw
MCP server + agent skill — lets AI agents drive a live Excalidraw canvas.
Vendored here under `external_sources/` for reference/tooling, not an
in-house project. See `README.md` in this directory for the full upstream
docs (setup, MCP tool list, troubleshooting).

## Running

```
port=3000 npm run canvas
```

Requires a local Excalidraw instance running (prereq).

## Session memory

At the start of a session, read `memory.md` in this directory for where
things left off. At the end of any session with real changes, update
`memory.md` (current state, next step, session log entry) and update this
project's row in `~/src/director_tasks.md`.
