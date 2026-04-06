# Agent Tools (`/src/tools`)

## Purpose
This directory contains the catalog of capabilities (tools) that the Claude Code model can invoke to interact with the local environment and external systems.

## Where this fits in the pipeline
Tools are the execution endpoints for the LLM. They are invoked by the `src/query` engine when the model determines an action is necessary to fulfill a request.

## Owns
* Tool implementation logic and execution routines.
* Input schema definitions (Zod) for validation.
* Capability-specific formatting of outputs back to the model.

## Does Not Own
* The decision of *when* to execute a tool (managed by the model via `/src/query`).
* User-invoked slash commands (see `/src/commands`).
* Global permission state management.

## Key files / Key subpaths
Tools are conceptually organized into functional categories, such as:
* **File System / I/O:** Reading, writing, and editing files (e.g., `FileReadTool`, `FileEditTool`).
* **Search:** Context gathering across the repository (e.g., `GrepTool`, `GlobTool`).
* **Execution:** Running local shell commands (e.g., `BashTool`).
* **Agents & Workflows:** Spawning sub-tasks or accessing remote MCP servers.

## Typical data / control flow
Query Engine requests tool execution → Tool receives validated schema → Tool performs action (e.g., reads file, runs bash) → Tool returns structured text result to the Query Engine.

## Read Next
* [Tools Reference](../../docs/tools.md)
* [Slash Commands](../commands/README.md)
