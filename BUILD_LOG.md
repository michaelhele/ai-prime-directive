# Build log

**Rules for this file (do not delete this block):**
- Append-only decision log, newest entry first. Never rewrite or delete past entries.
- Log only three things: design decisions (with the reasoning), pivots or reversals of earlier decisions, and completed milestones.
- Never log routine file creation, minor edits, refactors that change nothing architectural, or session start/end. That noise belongs nowhere.
- One to three sentences per entry, dated as 4 July 2026 style. Always include the *why*, not just the *what*; the why is the whole point of this file.
- If a logged decision turns out to be permanently binding (e.g. "never call the payments API directly"), promote it to an architectural constraint in AGENTS.md. The log records why; AGENTS.md records what still binds.
- Hard cap: when this log exceeds 100 entries, move the oldest 50 to BUILD_LOG_ARCHIVE.md (create it if absent, same newest-first format) and note the archival as an entry here.
- Do not import this file into standing context. It is read on demand, typically via PROJECT_HANDOVER.md's pointer, when someone needs the reasoning behind the current state.

## Decision log (newest first)
* **[Insert date]** — Repository initialised. AGENTS.md established as the single source of truth, PROJECT_HANDOVER.md as the shift-change document, and this file as the append-only decision log.
