# IDE Bridge (`/src/bridge`)

## Purpose
This directory implements a bidirectional communication layer that connects the Claude Code CLI with external IDE and editor extensions (like VS Code or JetBrains).

## Where this fits in the external integration architecture
When an IDE extension launches Claude Code, it uses this bridge to communicate. The bridge acts as a dedicated transport and protocol layer, routing messages between the IDE's UI/context and the CLI's internal engines.

## Owns
* The `bridgeMessaging.ts` protocol definition for IDE ↔ CLI communication.
* Message routing, serialization, and session management specifically for IDE clients.
* Proxying authorization or permission requests (e.g., `bridgePermissionCallbacks.ts`) so the IDE can handle UI prompts.
* JWT authentication utilities for securing the local connection.

## Does Not Own
* **Standalone Plugin Runtime:** Local plugins run within the CLI process, not over this bridge (see `/src/plugins`).
* **Generic Remote Daemon Hosting:** This is specifically for local IDE integration, not for hosting a remote server for multiple independent clients (see `/src/server`).
* **MCP Server Integration:** The Model Context Protocol is a separate standard used for tools and context, not for the core editor integration bridge (see `/mcp-server` or `src/entrypoints/mcp.ts`).

## External boundary / protocol boundary
This subsystem faces **local IDE extensions**. It typically communicates over standard I/O (stdio) or local secure sockets, using a custom messaging protocol defined within this directory.

## Key files / Key subpaths
* `bridgeMain.ts` - The primary initialization loop for the bridge mode.
* `replBridge.ts` - Logic for bridging the interactive REPL session to an IDE.
* `sessionRunner.ts` - Execution logic tied to a bridged session.

## Typical dependency direction
* **Depends on:** Core models, standard I/O streams, and local authentication utilities.
* **Depended on by:** The CLI entrypoint when launched in `--bridge` mode.

## How to read this folder
Start with `bridgeMain.ts` to see how the connection is established, then look at the messaging protocol files to understand the shape of the data flowing between the IDE and the CLI.

## Read Next
* [Subsystems Overview](../../docs/subsystems.md) - For a broader view of the bridge.
* [Plugins](../plugins/README.md) - To understand the difference between external IDEs and internal plugins.
