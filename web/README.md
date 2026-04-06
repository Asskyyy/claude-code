# Web Application (`/web`)

## 🎯 Purpose
This directory contains the source code for a web-based dashboard or interface associated with the Gemini CLI ecosystem, likely built with Next.js and Tailwind CSS.

## 🏛️ Domain Boundaries
* **Owns:** Web frontend UI components, web-specific API routes, page routing, and web styling.
* **Does NOT Own:** The core terminal CLI application (see `/src`), or the standalone MCP server logic (see `/mcp-server`).

## 🔑 Key Entry Files
* `next.config.ts` - Next.js configuration.
* `app/` - The Next.js App Router directory containing pages and layouts.
* `components/` - Reusable React components for the web UI.
* `lib/` - Shared utility functions for the web frontend.

## 🔄 Dependencies
* **Upstream (Depends on):** Next.js framework, React, Tailwind CSS, and potentially shared types or APIs from the broader project.
* **Downstream (Depended on by):** Users accessing the web interface.

## 📖 Read Next
* [Core Source Code](../src/README.md)
* [High-Level Architecture](../docs/architecture.md)
