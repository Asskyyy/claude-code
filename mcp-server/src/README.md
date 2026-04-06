# MCP Server Core (`/mcp-server/src`)

## Purpose
This directory contains the primary TypeScript source code implementing the standalone Claude Code Model Context Protocol (MCP) server. 

## Where this fits in the external integration architecture
This is part of the distinct `mcp-server/` sub-project. It implements a transport-agnostic MCP server that exposes specific Claude Code capabilities to *external* MCP clients (like Claude Desktop or Cursor). 

## Owns
* The definition of MCP tools, resources, and prompts exposed by this specific server.
* The core server lifecycle and request handling logic utilizing the `@modelcontextprotocol/sdk`.
* Transport-agnostic execution logic (it doesn't care if it's running via stdio or HTTP).

## Does Not Own
* **The Main Claude Code CLI Runtime:** The main interactive CLI logic lives in the root `/src` directory.
* **Claude Code as an MCP Client:** The logic where the CLI *consumes* other MCP servers lives elsewhere (e.g., `/src/services/mcp` or `src/tools/MCPTool.ts`).
* **Deployment Wrappers:** Specific HTTP or serverless adapters for this server live in `../api`.

## External boundary / protocol boundary
This subsystem faces **External MCP Clients**. It communicates strictly using the Model Context Protocol.

## Key files / Key subpaths
* `index.ts` / `server.ts` - The entrypoint and core MCP `Server` class instantiation.
* Tool implementation handlers specific to this MCP server.

## Typical dependency direction
* **Depends on:** `@modelcontextprotocol/sdk` and shared utilities from the main project.
* **Depended on by:** The entrypoints in `/mcp-server/api` or `src/entrypoints/mcp.ts` that attach transports (stdio/HTTP) to this core logic.

## How to read this folder
Read this as a standard, self-contained MCP server implementation. Look at how tools are registered and how requests are handled using the official SDK.

## Read Next
* [MCP API Wrappers](../api/README.md) - To see how this core logic is deployed via HTTP/serverless.
* [Root MCP README](../../mcp-server/README.md) - For the overarching documentation of this sub-project.
* [CLI MCP Entrypoint](../../src/entrypoints/README.md) - To see how the main CLI exposes MCP functionality.
