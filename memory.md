# Session Memory — external_sources/mcp_excalidraw

**Last updated:** 2026-07-14
**Status:** Prototype — vendored third-party MCP server, used to test block diagram generation

## Current state
Jim is using this MCP server to test block diagram generation. Output
diagrams from these tests are saved to `~/src/excalidraw_examples/`, which
holds the diagram conventions (orthogonal lines, thin-rect rules) and saved
examples. See `README.md` here for upstream setup/tool docs.

## Next step
Continue testing block diagram generation; save useful outputs/conventions to `../excalidraw_examples/`. Old xlsx tracker also had a vague note — "some progress, link to Cowork?" — meaning not pinned down; ask Jim if relevant.

## Open questions / blockers
None currently.

## Session log
- 2026-07-14: Added this file and `CLAUDE.md` to bring this project under the multi-session director-tracking pattern (see `../../director_tasks.md`). Clarified purpose: testing block diagram generation, outputs go to `excalidraw_examples/`. No code changes.
- 2026-07-15: Migrated `npm run canvas` run command into `CLAUDE.md` from the retired `claude_project_tracker.xlsx` row.
