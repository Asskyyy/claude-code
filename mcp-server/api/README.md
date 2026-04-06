# MCP Server API Wrappers (`/mcp-server/api`)

## 🎯 Purpose
This directory provides the serverless function wrappers required to deploy the MCP server logic to platforms like Vercel.

## 🏛️ Domain Boundaries
* **Owns:** HTTP request/response translation layers for serverless environments.
* **Does NOT Own:** The core MCP implementation logic itself (see `/mcp-server/src`).

## 🔑 Key Entry Files
* `index.ts`, `vercelApp.ts` - Serverless entry handlers.

## 🔄 Dependencies
* **Upstream (Depends on):** `/mcp-server/src` for the core logic, and serverless framework APIs.
* **Downstream (Depended on by):** Cloud deployment infrastructure.

## 📖 Read Next
* [MCP Server Core](../src/README.md)
