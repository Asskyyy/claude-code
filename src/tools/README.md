# Agent Tools (`/src/tools`)

## 🎯 Purpose
This directory contains the catalog of self-contained tools that the Claude agent can invoke to interact with the file system, network, or external systems.

## 🏛️ Domain Boundaries
* **Owns:** Tool logic implementations, input schema definitions (Zod), and specific permission models for each tool (e.g., `FileReadTool`, `BashTool`).
* **Does NOT Own:** The query execution loop that calls them (see `/src/query`), or user-facing slash commands (see `/src/commands`).

## 🔑 Key Entry Files
* `index.ts` - Tool registry exporting all available tools to the query engine.
* Individual tool implementations (e.g., file tools, bash execution).

## 🔄 Dependencies
* **Upstream (Depends on):** External subsystems (File System, OS, network).
* **Downstream (Depended on by):** The Query Engine (`/src/query`), which provides the LLM's tool calls.

## 📖 Read Next
* [High-Level Tools Reference](../../docs/tools.md)
* [Commands](../commands/README.md)
