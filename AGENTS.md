# AGENTS.md

[USER ACTION REQUIRED: Fill in the bracketed sections below to initialise the project. Keep this whole file under roughly 150 lines. Agents follow short, specific files far better than long ones. If a rule is only enforced by a linter or formatter, leave it out; that is the linter's job.]

This file is the single source of truth for this repository. Every AI coding agent that supports the AGENTS.md standard (Cursor, Codex, GitHub Copilot, Google Jules, Windsurf, Cline, Antigravity and others) reads it automatically. Tools that do not are pointed here by a thin import file (see CLAUDE.md, GEMINI.md).

## Project scope
[Insert a short description of what this project does.]

## Tech stack
[Insert languages, frameworks, key dependencies.]

## Build and test commands
[Insert the exact commands agents should run, e.g. how to install dependencies, run the dev server, run the test suite, and lint. This is the most useful section in the file. Be literal: `npm install`, `npm test`, etc.]

## Coding conventions
[Insert style rules, naming conventions, testing requirements. Only include rules a tool does not already enforce.]

## Architectural constraints
[Insert anything agents must never do: files not to touch, patterns not to introduce, services not to call. Give a one-line reason for each; agents apply a constraint better when they know why it exists.]

## Shift protocol (session handover)
This project uses a hospital-style shift handover between sessions.

1. **Start of your first session on this project:** read PROJECT_HANDOVER.md in full before making changes. It tells you the current state, what is in flight, and which decisions are settled.
2. **During the session:** when you make a design decision, reverse an earlier one, or complete a milestone, append an entry to BUILD_LOG.md following the rules in its header. Never log routine file creation or minor edits.
3. **End of the session:** update PROJECT_HANDOVER.md before finishing. Rewrite the current-state summary, and add yourself to the recent-shifts list per the rules in that file.

Do not import or routinely reload PROJECT_HANDOVER.md or BUILD_LOG.md into standing context. They are read on demand, once, at the points described above.

## Reusable skills
Reusable agent skills live in `.agents/skills/`. Check there for an existing skill before writing new logic. (Note: Claude Code stores skills under `.claude/` instead; treat `.agents/skills/` as the shared location and mirror manually if needed.)
