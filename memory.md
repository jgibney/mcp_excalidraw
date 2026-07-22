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
- 2026-07-22: Closing git-coverage gaps across `~/src`, found this local clone had an uncommitted patch (widening the label schema to accept `fontFamily`/`fontSize` — see `feedback-excalidraw-label-fontfamily` in the global memory system) plus an already-existing unpushed commit, and `CLAUDE.md`/`memory.md` were never tracked at all. `origin` points at the upstream `yctimlin/mcp_excalidraw` (no push access, as expected for someone else's project) — but `gh repo fork` revealed **a fork already exists** at `jgibney/mcp_excalidraw` with substantial additional work (many feature branches: `feat/canvas-toolkit-v2`, `fix/arrow-binding-preservation`, etc.) and a `main` ahead of this local clone. To avoid clobbering that, pushed this session's commit to a new branch, `local-fixes`, on the fork rather than overwriting `main` — see https://github.com/jgibney/mcp_excalidraw/tree/local-fixes. **Worth a future session reconciling this local clone with the more advanced fork** rather than treating this directory as the authoritative copy going forward. Confirmed the upstream `origin/main` has moved further ahead too (6 new commits as of this check) — reconciliation needs to account for three diverged copies (local, fork, upstream), not just two.
- 2026-07-22 (later, new session): reproduced a CPU pipeline diagram via the running MCP server (`cpu_decode_pipeline.excalidraw` in `../excalidraw_examples/`, see that project's memory.md for the T-bar drop-arrow diagonal-rendering fix found along the way). **Found the running server instance (PID active since 2026-07-21, i.e. before the ~/src Dropbox rollback) still enforces the old `/home/jim/Dropbox/src/...` path as its allowed export directory** — `export_scene`/`export_to_image` reject the new `~/src/...` path with "Path traversal blocked." Worked around by exporting to the old (still-existing, untouched-backup) Dropbox path and `mv`-ing the file over afterward. Restarting the MCP server process would let it pick up the current path properly — worth doing next time it's convenient, since this'll keep biting exports otherwise. This server is also what backs the `mcp__excalidraw__*` tools available directly in Claude Code sessions, not just something Jim runs manually.
