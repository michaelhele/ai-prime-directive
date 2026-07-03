# AI Prime Directive Framework

A centralised routing and handover system for AI coding agents: project rules written once and read by every tool, plus a hospital-style shift handover so any new agent, model or machine can pick the project up cold.

## Core architecture

* **AGENTS.md** — the single source of truth for all AI instructions and repository rules. An open, cross-tool standard, originally a collaboration between Sourcegraph, OpenAI, Google, Cursor and Factory, now stewarded by the Agentic AI Foundation under the Linux Foundation. Read natively by Cursor, Codex, GitHub Copilot, Google Jules, Windsurf, Cline, Antigravity and others. This is the only file loaded into standing context on every prompt, so it stays lean: aim for under 150 lines.
* **PROJECT_HANDOVER.md** — the whiteboard at the nurses' station. A fixed-size, fully overwritten document holding the current state (max 20 lines), what is in flight, which decisions are settled, and the last three sessions ("who was on shift": tool, model, date). Read once at the start of a session, updated once at the end. It never grows, so it never needs archiving and never bloats context.
* **BUILD_LOG.md** — the patient notes. An append-only log of design decisions, pivots and milestones, newest first, always recording the reasoning. Not loaded into context; consulted on demand when someone needs to know *why* the project looks the way it does. At 100 entries the oldest half moves to **BUILD_LOG_ARCHIVE.md**.
* **.agents/skills/** — a shared folder for reusable agent skills, read by Antigravity and Gemini tooling. Claude Code currently keeps skills under `.claude/` instead, so treat this as the shared location and mirror where needed.

## Redirect files

A minority of tools still do not read AGENTS.md by default and need a thin pointer:

* **CLAUDE.md** — Claude Code reads CLAUDE.md rather than AGENTS.md. Rather than a prose instruction ("go and read AGENTS.md"), which relies on the model choosing to obey, the file uses Claude Code's `@AGENTS.md` import syntax, which loads the master file mechanically at session start.
* **GEMINI.md** — a safety net for older Gemini CLI setups. Recent Google tooling (Antigravity, and Gemini CLI with `context.fileName` configured) reads AGENTS.md natively; where it does not, this file imports it via `@./AGENTS.md`.

Do not duplicate content into these files. They contain nothing but the import.

**Why imports rather than symlinks?** Symlinks (`ln -s AGENTS.md CLAUDE.md`) work well on macOS and Linux but are unreliable on Windows, where they require developer mode or elevated permissions and can arrive as plain text files after a git clone. The import files are ordinary text, behave identically on every operating system, and survive any clone. The framework standardises on imports and does not use symlinks at all.

## How it works

**1. One set of rules, read by everything.**
Define project scope, stack, build and test commands, conventions and constraints once in AGENTS.md. Most agents read it natively; the two pointer files mechanically import it for the rest.

**2. Shift handover, not total recall.**
When a new session starts, whether that is a different model, a different IDE, or the same setup on a different machine, the agent reads PROJECT_HANDOVER.md once and is up to speed, exactly as an incoming nurse gets the highlights at shift change rather than the patient's entire history. If it needs the reasoning behind a settled decision, the full notes are in BUILD_LOG.md.

**3. Hard caps against bloat.**
Every file has a size discipline. AGENTS.md targets 150 lines. The handover summary is capped at 20 lines and the shift list at 3 entries. The build log archives at 100 entries. Without hard limits these files grow until neither agents nor humans read them.

**4. A promotion path for decisions.**
A decision starts life as a build-log entry. If it proves permanently binding, it is promoted to an architectural constraint in AGENTS.md. The log records why; AGENTS.md records what still binds.

## Background

Michael Hele's background spans manufacturing, web design and marketing. He draws a direct comparison between the two: standardised components lowered cost and improved consistency in manufacturing, in much the same way global stylesheets replaced page-by-page styling in web design. This framework applies the same logic to AI coding agents: one set of rules, defined once, read consistently by every tool, with a clean handover when the tool changes.

More on his background: [michaelhele.com](https://michaelhele.com/)

## Further reading

The full case for the framework, including the reasoning behind standardising on `AGENTS.md`: [AI Prime Directive: The Logical Fix](https://www.businessgrowthready.com/ai-prime-directive-logical-fix/)

## Contact

Built and maintained by Michael Hele at [AMD Creative Marketing](https://amdcreativemarketing.com/).

## Licence

MIT. See [`LICENSE`](./LICENSE) for details.
