# MCP Server API Wrappers (`/mcp-server/api`)

## Purpose
This directory provides the specific deployment adapters and HTTP serverless function wrappers required to host the standalone MCP server on platforms like Vercel.

## Where this fits in the external integration architecture
This sits at the very edge of the `mcp-server/` sub-project. It takes the transport-agnostic core logic from `../src` and attaches an HTTP transport layer (Server-Sent Events or standard HTTP endpoints) suitable for cloud deployment.

## Owns
* HTTP request and response translation layers.
* Serverless environment entry handlers (e.g., for Vercel or AWS Lambda).
* Attaching the HTTP transport to the core MCP Server instance.

## Does Not Own
* **Core MCP Protocol Logic:** The actual tool definitions and server behaviors live in `../src`.
* **stdio Transport:** Local stdio-based execution is typically handled by the main CLI (`src/entrypoints/mcp.ts`) or `../src/index.ts`, not here.

## External boundary / protocol boundary
This subsystem faces **Cloud Load Balancers and HTTP Clients**. The boundary is standard HTTP/1.1 or HTTP/2 (SSE), wrapping the underlying MCP JSON-RPC messages.

## Key files / Key subpaths
* `index.ts`, `vercelApp.ts` - Serverless function entry points.

## Typical dependency direction
* **Depends on:** `/mcp-server/src` (for the core server logic) and serverless framework APIs (like Vercel's `Request`/`Response` types).
* **Depended on by:** The cloud deployment infrastructure mapping routes to these files.

## How to read this folder
Understand this as a thin adapter layer. It receives an HTTP request, translates it into something the MCP SDK understands, passes it to `../src`, and translates the response back to HTTP.

## Read Next
* [MCP Server Core](../src/README.md) - To understand the logic being wrapped by these HTTP endpoints.
* [Root MCP README](../../mcp-server/README.md) - For deployment instructions.
