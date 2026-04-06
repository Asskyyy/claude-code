# Plugin System (`/src/plugins`)

## Purpose
This directory manages the lifecycle, loading, and resolution of third-party or built-in plugins that run *within* the Claude Code CLI process to extend its capabilities.

## Where this fits in the external integration architecture
Plugins are local, installable extensions that run in the same environment as the CLI. They are an internal extension surface, distinct from external networked servers (like MCP) or external IDEs (like the Bridge).

## Owns
* Plugin resolution and loading mechanisms from the local file system or `node_modules`.
* The API surface (SDK) exposed to loaded plugins.
* Lifecycle hooks (init, teardown) for plugin execution.
* Sandbox or isolation controls (if applicable) for running third-party code safely.

## Does Not Own
* **Markdown-based "Skills":** Skills are prompt/instruction packages (see `/src/skills`); plugins are executable JavaScript/TypeScript modules.
* **External MCP Servers:** Plugins run locally; MCP servers are typically standalone processes communicated with over stdio/HTTP.
* **Core Tool Implementations:** While plugins *might* register tools, the core built-in tools live in `/src/tools`.

## External boundary / protocol boundary
This subsystem faces **local developers and plugin authors**. The boundary is the JavaScript/TypeScript API exposed by the CLI for plugins to consume.

## Key files / Key subpaths
* Plugin loader/registry implementations.
* API definition files that represent the contract between Claude Code and the plugin.

## Typical dependency direction
* **Depends on:** File system (for resolution), module loading APIs, and core CLI state.
* **Depended on by:** The main CLI initialization sequence.

## How to read this folder
Look for the loader logic to understand how plugins are discovered, and examine the API export files to understand what capabilities a plugin is granted once loaded.

## Read Next
* [Skills](../skills/README.md) - To understand the difference between executable plugins and instructional skills.
* [MCP Server Core](../../mcp-server/src/README.md) - To understand external networked extensions.
