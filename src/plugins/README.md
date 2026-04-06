# Plugin System (`/src/plugins`)

## 🎯 Purpose
This directory manages the dynamic loading and lifecycle of third-party or built-in plugins that extend the CLI's capabilities.

## 🏛️ Domain Boundaries
* **Owns:** Plugin resolution, loading mechanisms, API surface exposed to plugins, and sandbox controls.
* **Does NOT Own:** Markdown-based "Skills" (see `/src/skills`), or external MCP servers.

## 🔑 Key Entry Files
* Plugin loader and registry logic.

## 🔄 Dependencies
* **Upstream (Depends on):** File system and module loading subsystems.
* **Downstream (Depended on by):** Core CLI initialization.

## 📖 Read Next
* [Skills](../skills/README.md)
