# MCP Server Core (`/mcp-server/src`)

## 🎯 Purpose
This directory contains the primary TypeScript source code implementing the standalone Model Context Protocol (MCP) server.

## 🏛️ Domain Boundaries
* **Owns:** The MCP tool definitions, resource handling, and server lifecycle logic specifically for this MCP distribution.
* **Does NOT Own:** The agent CLI execution loop (see `../../src/query`), or Vercel serverless wrappers (see `/mcp-server/api`).

## 🔑 Key Entry Files
* `index.ts` / `server.ts` - The entrypoint and core server class.

## 🔄 Dependencies
* **Upstream (Depends on):** The `@modelcontextprotocol/sdk`.
* **Downstream (Depended on by):** MCP clients (Claude Desktop, VS Code, etc.).

## 📖 Read Next
* [MCP API Handlers](../api/README.md)
