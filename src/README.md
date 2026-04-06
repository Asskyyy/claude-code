# Core Source Code (`/src`)

## Purpose
This directory houses the core executable source code for Claude Code. It contains the runtime, terminal UI, agent orchestration, and integrations with external systems.

## Owns
* The primary CLI execution lifecycle and command parsers.
* React/Ink terminal UI components and state management.
* Agent tool execution loop, built-in skills, and tasks.

## Does Not Own
* Standalone MCP servers (see `/mcp-server`).
* Web dashboards (see `/web`).
* Human-readable architectural documentation (see `/docs`).

## Key Entry Files
* `main.tsx` - The main entry point that initializes the React+Ink application and bootstraps the CLI.
* `commands.ts` / `tools.ts` - Top-level registries for CLI commands and agent tools.
* `QueryEngine.ts` - The core engine that handles LLM interactions and tool execution loops.

## Read Next
* [High-Level Architecture](../docs/architecture.md)
* [Subsystems Overview](../docs/subsystems.md)
* [Entrypoints & CLI](entrypoints/README.md)