# AI Prime Directive Framework

A named method for standardising how developers work across multiple AI coding agents on the same project. It doesn't introduce new technology. It packages an existing open standard, `AGENTS.md`, into a disciplined practice: one master file, thin pointer files for tools that haven't adopted it yet, and a running build log so a new agent isn't starting cold.

## What it overcomes

Developers increasingly run several AI coding agents on the same project, command-line tools such as Claude Code, IDE-based agents such as Cursor and Windsurf, and autonomous engines running independently on a server. Each has traditionally needed its own configuration file, so rules and context set up for one model don't carry over when you switch to another.

`AGENTS.md` was created to solve this. It emerged in August 2025 as a joint effort between OpenAI, Google, Cursor and other industry partners, and in December 2025 was contributed to the Agentic AI Foundation, which now stewards it as an open standard. Most tools read it natively. The gap this framework closes is the handful that still don't.

There's a second problem it addresses: the cold start. When a developer brings in a new agent partway through a project, that agent can read the code but has no record of why decisions were made. A build log fixes that.

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
