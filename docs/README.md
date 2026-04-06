# Documentation (`/docs`)

## 🎯 Purpose
This directory contains the high-level, human-readable architectural documentation and system guides for the Gemini CLI. It serves as the canonical reference for understanding how the system is designed at a macro level.

## 🏛️ Domain Boundaries
* **Owns:** System architecture diagrams, subsystem definitions, tool and command references, and exploration guides for new contributors.
* **Does NOT Own:** Raw prompt design notes (see `/prompts`), directory-specific code routing (handled by local `README.md` files), or user-facing installation instructions (see root `README.md`).

## 🔑 Key Entry Files
* `architecture.md` - The primary guide detailing the main execution pipeline (User Input → CLI Parser → Query Engine → LLM API → Tool Execution Loop → Terminal UI).
* `subsystems.md` - Definitions of independent subsystems (e.g., Skills, Memory, Coordinator, Bridge).
* `tools.md` / `commands.md` - Reference documentation for available agent tools and CLI commands.

## 🔄 Dependencies
* **Upstream (Depends on):** System design decisions and current implementation state in `/src`.
* **Downstream (Depended on by):** New contributors reading the repository, and AI agents looking for context (`.gemini/skills`).

## 📖 Read Next
* [Core Source Code](../src/README.md)
* [Prompt Engineering Notes](../prompts/README.md)
