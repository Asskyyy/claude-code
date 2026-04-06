# Core Source Code (`/src`)

## 🎯 Purpose
This is the primary source directory for the Gemini CLI application. It houses the core execution runtime, the terminal UI, the plugin/agent orchestration system, and the integration layer with external environments.

## 🏛️ Domain Boundaries
* **Owns:** The core CLI execution lifecycle, React/Ink terminal UI components, command parsers, tool execution loop, state management, and built-in skills/tasks.
* **Does NOT Own:** Standalone MCP servers (see `/mcp-server`), web dashboards (see `/web`), or raw prompt engineering notes (see `/prompts`).

## 🔑 Key Entry Files
* `main.tsx` - The main entry point that initializes the React+Ink application and bootstraps the CLI.
* `commands.ts` / `tools.ts` - Top-level registries for CLI commands and agent tools.
* `setup.ts` - Initial configuration and environment setup.
* `QueryEngine.ts` - The core engine that handles LLM interactions and tool execution loops.

## 🔄 Dependencies
* **Upstream (Depends on):** The underlying runtime (Node.js/Bun), local file system, and external LLM APIs (via HTTP/MCP).
* **Downstream (Depended on by):** Build scripts in `/scripts`, and external IDE integrations (via `/src/bridge`).

## 📖 Read Next
* [High-Level Architecture](../../docs/architecture.md)
* [Subsystems Overview](../../docs/subsystems.md)
* [Entrypoints & CLI](entrypoints/README.md)
