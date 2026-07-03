# AGENTS.md

[USER ACTION REQUIRED: Insert your core project instructions, architectural constraints, tech stack and styling guidelines here to initialise the project.]

This file is the single source of truth for this repository. Every AI coding agent that supports the AGENTS.md standard (Cursor, Codex, GitHub Copilot, Google Jules, Windsurf, Roo Code, and others) will read it automatically. Tools that do not yet support the standard are pointed here by a short redirect file (see CLAUDE.md, GEMINI.md).

## Project scope
[Insert a short description of what this project does.]

## Tech stack
[Insert languages, frameworks, key dependencies.]

## Coding conventions
[Insert style rules, naming conventions, testing requirements.]

## Architectural constraints
[Insert anything agents must never do: files not to touch, patterns not to introduce, services not to call.]

## Process rules
- Maintain BUILD_LOG.md throughout the project. Every time a file is created, a design decision is made, or a significant step is completed, append a dated entry in plain English.
- Reusable agent skills live in .agents/skills/. Check there for an existing skill before writing new logic.

## Before you start
Read BUILD_LOG.md before making changes. It records why the project looks the way it does, not just what the code currently does.
