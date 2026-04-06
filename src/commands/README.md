# Slash Commands (`/src/commands`)

## 🎯 Purpose
This directory implements the user-facing slash commands (e.g., `/commit`, `/mcp`, `/review`) available within the interactive CLI REPL.

## 🏛️ Domain Boundaries
* **Owns:** The logic executed when a user types a command, argument parsing for those commands, and corresponding terminal feedback.
* **Does NOT Own:** Agent-invoked tools (see `/src/tools`) or the underlying REPL UI rendering (see `/src/components`).

## 🔑 Key Entry Files
* `index.ts` - Command registry exporting all slash commands.
* Command files (e.g., `commit.ts`, `config.ts`, `review.ts`).

## 🔄 Dependencies
* **Upstream (Depends on):** The underlying services and subsystem states.
* **Downstream (Depended on by):** The REPL input handler (`/src/cli` and `main.tsx`).

## 📖 Read Next
* [High-Level Commands Reference](../../docs/commands.md)
* [Agent Tools](../tools/README.md)
