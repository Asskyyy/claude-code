# Entrypoints (`/src/entrypoints`)

## Purpose
This directory handles the bootstrapping, initialization, and mode selection for Claude Code.

## Where this fits in the pipeline
This is the absolute beginning of the application lifecycle. It accepts the initial process execution, parses top-level arguments, and routes control to the appropriate subsystem (e.g., the interactive CLI, MCP server mode, or programmatic SDK).

## Owns
* Process initialization and bootstrapping.
* High-level routing and mode switching.
* Wiring up initial environment dependencies.

## Does Not Own
* The core conversational loop (see `/src/query`).
* Tool logic or execution (see `/src/tools`).
* UI rendering details (see `/src/components`).

## Key files / Key subpaths
* `cli.tsx` - The entry point for the standard interactive terminal UI.
* `init.ts` - Core bootstrapping and shared initialization logic.
* `mcp.ts` - Entry point for running Claude Code as an MCP server.
* `sdk/` - Subpath for programmatic SDK exports.

## Typical data / control flow
`process.argv` → Argument Parsing/Validation → Mode Selection (CLI/MCP/SDK) → Handoff to `QueryEngine` or UI Root.

## Read Next
* [Query Engine](../query/README.md)
* [High-Level Architecture](../../docs/architecture.md)
