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
- 2026-07-22: Closing git-coverage gaps across `~/src`, found this local clone had an uncommitted patch (widening the label schema to accept `fontFamily`/`fontSize` — see `feedback-excalidraw-label-fontfamily` in the global memory system) plus an already-existing unpushed commit, and `CLAUDE.md`/`memory.md` were never tracked at all. `origin` points at the upstream `yctimlin/mcp_excalidraw` (no push access, as expected for someone else's project) — but `gh repo fork` revealed **a fork already exists** at `jgibney/mcp_excalidraw` with substantial additional work (many feature branches: `feat/canvas-toolkit-v2`, `fix/arrow-binding-preservation`, etc.) and a `main` ahead of this local clone. To avoid clobbering that, pushed this session's commit to a new branch, `local-fixes`, on the fork rather than overwriting `main` — see https://github.com/jgibney/mcp_excalidraw/tree/local-fixes. **Worth a future session reconciling this local clone with the more advanced fork** rather than treating this directory as the authoritative copy going forward.
