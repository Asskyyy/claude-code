# Documentation (`/docs`)

## Purpose
This directory contains the high-level, human-readable architectural documentation and system guides for Claude Code. It serves as the primary reference for understanding the system design at a macro level.

## Owns
* System architecture descriptions and diagrams.
* Subsystem definitions (e.g., Skills, Memory, Coordinator, Bridge).
* Tool and command capability references.
* Exploration guides for new contributors.

## Does Not Own
* Raw prompt design or historical research notes (see `/prompts`).
* Directory-specific code routing (handled by local `README.md` files).
* Executable source code (see `/src`).

## Key Entry Files
* `architecture.md` - Details the main execution pipeline (User Input → CLI Parser → Query Engine → LLM API → Tool Execution Loop → Terminal UI).
* `subsystems.md` - Outlines independent subsystems.
* `tools.md` / `commands.md` - Reference documentation for available agent tools and CLI slash commands.

## Read Next
* [Core Source Code](../src/README.md)
* [Prompt Engineering Notes](../prompts/README.md)