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

## How it works

**1. `AGENTS.md` as the single source of truth**
Define project rules, conventions and context once, in the format most agents already read natively.

**2. Pointer files for holdouts**
For tools that don't yet read `AGENTS.md` (Claude Code among them), add a short file in that tool's expected location that redirects it back to the master file, rather than letting a second, conflicting set of instructions build up.

**3. `BUILD_LOG.md` for continuity**
A plain-text log of design decisions, pivots and milestones, updated as the project moves. Any newly introduced agent, or human collaborator, can read it and continue work without re-litigating earlier choices.

## Background

Michael Hele's background spans manufacturing, web design and marketing. He draws a direct comparison between the two: standardised components lowered cost and improved consistency in manufacturing, in much the same way global stylesheets replaced page-by-page styling in web design. This framework applies the same logic to AI coding agents, one set of rules, defined once, read consistently by every tool.

More on his background: [michaelhele.com](https://michaelhele.com/)

## Further reading

The full case for the framework, including the reasoning behind standardising on `AGENTS.md`: [AI Prime Directive: The Logical Fix](https://www.businessgrowthready.com/ai-prime-directive-logical-fix/)

## Contact

Built and maintained by Michael Hele at [AMD Creative Marketing](https://amdcreativemarketing.com/).

## Licence

MIT. See [`LICENSE`](./LICENSE) for details.
