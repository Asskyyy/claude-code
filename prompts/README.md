# Prompt Engineering Notes (`/prompts`)

## Purpose
This directory contains a numbered series of research notes, prompt engineering guides, and contextual explanations detailing how various parts of Claude Code were built and designed. It is meant to provide historical rationale and system context for LLMs or developers studying the repository.

## How to use this folder
These documents serve as chronological and thematic research notes. They explain the "why" and "how" behind specific design decisions, rather than acting as strict runtime documentation. They are particularly useful for understanding the iterative development of Claude Code's capabilities.

## Recommended reading order
Read `00-overview.md` first to understand the general strategy. After that, you can read chronologically or jump directly to the subsystem you are investigating based on the file names.

## File-by-file index
* `00-overview.md` - High-level summary of the repository's prompt and agent strategy.
* `01-install-bun-and-deps.md` - Notes on runtime selection (Bun) and dependency management.
* `02-runtime-shims.md` - Context on handling Node.js vs. Bun compatibility.
* `03-build-config.md` - Configuration strategies for building the project.
* `04-fix-mcp-server.md` - Context and fixes regarding the MCP server integration.
* `05-env-and-auth.md` - Details on environment variable handling and authentication.
* `06-ink-react-terminal-ui.md` - Explanations of the terminal UI built with React and Ink.
* `07-tool-system.md` - Rationale behind the agent tool system design.
* `08-command-system.md` - Design notes for the user-facing slash command system.
* `09-query-engine.md` - Notes on the core LLM execution loop and context management.
* `10-context-and-prompts.md` - Guidelines on general prompt injection and context window strategies.
* `11-mcp-integration.md` - Deep dive into integrating Model Context Protocol concepts.
* `12-services-layer.md` - Explanations of the external integrations and infrastructure services.
* `13-bridge-ide.md` - Context for the bidirectional IDE integration layer.
* `14-dev-runner.md` - Notes on the local development setup.
* `15-production-bundle.md` - Strategy for bundling the CLI for production release.
* `16-testing.md` - Approaches and context for testing the various systems.

## Does Not Own
* Formal human-facing system architecture documentation (see `/docs`).
* Executable application code or production prompts loaded directly by the runtime (see `/src`).

## Read Next
* [High-Level Architecture](../docs/architecture.md)
* [Subsystems Overview](../docs/subsystems.md)