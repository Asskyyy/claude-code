# Web Application (`/web`)

## Purpose
This directory contains the source code for a web-based interface or dashboard associated with the Claude Code ecosystem, implemented using Next.js and Tailwind CSS.

## Owns
* Web frontend UI components.
* Web-specific API routes and page routing.
* Styling logic for the web application.

## Does Not Own
* The core terminal CLI application (see `/src`).
* The standalone MCP server implementation (see `/mcp-server`).

## Key Entry Files
* `next.config.ts` - Next.js framework configuration.
* `app/` - The Next.js App Router directory.
* `components/` - Reusable React components for the web UI.

## Read Next
* [Core Source Code](../src/README.md)