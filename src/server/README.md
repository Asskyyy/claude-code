# Server Mode (`/src/server`)

## Purpose
This directory provides the infrastructure for running Claude Code as a persistent, background daemon or hosted server, allowing remote sessions to connect to it.

## Where this fits in the external integration architecture
This is the **Host Side** of a remote execution architecture. It binds to a port and listens for incoming connections from separate Claude Code clients, allowing heavy execution or state to live on a remote machine.

## Owns
* Server lifecycle management (start, stop, backgrounding).
* Port binding, networking, and accepting incoming remote connections.
* Hosting the core CLI engine and maintaining state for connected clients.

## Does Not Own
* **The Client Side:** The logic for connecting *to* this server lives in `/src/remote`.
* **IDE Integration:** The server mode is for generic remote sessions, not the specific IDE bridge protocol (see `/src/bridge`).
* **Standalone MCP Servers:** This hosts the Claude Code CLI itself, it is not an MCP server (see `mcp-server/README.md` or `src/entrypoints/mcp.ts` for MCP mode).

## External boundary / protocol boundary
This subsystem faces **Remote Claude Code Clients**. The boundary is the network port it binds to and the protocol it uses to sync terminal state and commands with the remote client.

## Key files / Key subpaths
* Core server initialization logic.
* Request/connection handlers.

## Typical dependency direction
* **Depends on:** Node/Bun networking APIs, core QueryEngine.
* **Depended on by:** The CLI entrypoint when launched in daemon/server mode.

## How to read this folder
Focus on how the server is instantiated, how it binds to the network, and how it delegates incoming requests to the underlying `QueryEngine` or state manager.

## Read Next
* [Remote Sessions](../remote/README.md) - To see how a client connects to this server.
* [Entrypoints](../entrypoints/README.md) - To see how the server mode is launched.
