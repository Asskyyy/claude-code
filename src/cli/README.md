# CLI Parsing (`/src/cli`)

## 🎯 Purpose
This directory contains the command-line interface parsing logic, routing the raw terminal arguments into structured commands or interactive sessions.

## 🏛️ Domain Boundaries
* **Owns:** Parsing command-line arguments, handling basic flag logic (e.g., `--help`, `--version`), and delegating to specific operational modes.
* **Does NOT Own:** Interactive command logic (see `/src/commands`) or LLM interactions (see `/src/query`).

## 🔑 Key Entry Files
* Handlers for specific CLI flags and initial parsed outputs.

## 🔄 Dependencies
* **Upstream (Depends on):** CLI frameworks (like Commander.js).
* **Downstream (Depended on by):** Core query engine and commands execution.

## 📖 Read Next
* [Commands](../commands/README.md)
* [Query Engine](../query/README.md)
