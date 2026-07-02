# AI Prime Directive Framework

A centralised routing system for AI coding agents, so project rules are written once and read by every tool.

## Core architecture

* **AGENTS.md** — the single source of truth for all AI instructions and repository rules. This is the open, cross-tool standard originally published by OpenAI and now stewarded by the Agentic AI Foundation. It is read natively by Cursor, Codex, Gemini CLI, GitHub Copilot, Google Jules, Windsurf, Roo Code and others.
* **BUILD_LOG.md** — a plain-English chronological diary of design decisions, file creations and project milestones. Prevents "cold start" when a new agent or human joins the project.
* **_skills/** — a storage location for modular workflows and specialised agent prompts.

## Redirect files

A small number of tools do not yet read AGENTS.md natively and require a thin pointer file instead:

* **CLAUDE.md** — for Claude Code.
* **GEMINI.md** — safety-net redirect for Gemini-based tools, in case AGENTS.md is not picked up automatically.

Do not duplicate content into these files. They exist only to redirect an agent back to AGENTS.md.

## Maintenance rules for humans

1. Never update the redirect files with project content. If you need to change coding conventions, add dependencies, or modify documentation requirements, make the change exclusively in AGENTS.md.
2. Keep filenames exact. Changing capitalisation can cause an agent to miss the file entirely.
3. Log significant changes in BUILD_LOG.md so both human contributors and AI agents can follow the project's history.

## How to initialise a new project via chat

If you are using a command-line agent, you can configure the whole repository through natural language without opening a text editor. Send this to your active AI agent:

> "Update AGENTS.md with the new project scope [insert your tech stack, goals and rules], and document this initialisation step in BUILD_LOG.md."

The agent will populate the master rule file and create the first entry in the build log.

## Adding support for a new tool

If a new AI coding tool launches that requires its own proprietary filename, add one more thin redirect file pointing back to AGENTS.md. The core instructions in AGENTS.md never need to change.

---
Prime Directive Framework created by Michael Hele
🌐 michaelhele.com
Licensed under the MIT License.
