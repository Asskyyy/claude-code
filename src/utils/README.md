# Utilities (`/src/utils`)

## Purpose
This directory contains pure, stateless helper functions that provide highly reusable, domain-agnostic logic across the Claude Code application.

## Where this fits in the runtime / foundation architecture
This is a **stateless computation layer**. It provides building blocks for common operations (like formatting text, manipulating arrays, or doing math) that don't depend on or alter the global application state or external systems.

## Owns
* Pure functions with predictable inputs and outputs.
* String manipulation and formatting helpers.
* Basic file path normalization helpers.
* Data structure transformers.

## Does Not Own
* **Anything with side-effects:** Network calls, reading from disk, or modifying global state do not belong here (see `/src/services`).
* **Domain-specific orchestration:** Complex business rules specific to a single feature should live near that feature, not here.
* **This is NOT a dumping ground:** If a function only serves the Query Engine, it belongs in `/src/query`, not `/src/utils`.

## Boundary with adjacent foundation layers
* **Vs. Services:** Utils are pure functions (`f(x) -> y`). Services manage external integrations, stateful clients, and side-effects.
* **Vs. Constants:** Utils are functions; constants are static values.

## Key files / Key subpaths
* Pure utility functions grouped by common categories (e.g., string utils, math utils).

## Typical dependency direction
* **Depends on:** Node/Bun built-ins and potentially `/src/constants`.
* **Depended on by:** Broadly across the application.

## How to read this folder
If you find yourself writing a standard data manipulation function (like camel-casing a string or debouncing a callback), check here first to see if a robust, tested version already exists.

## Read Next
* [Constants](../constants/README.md) - For the static values these utils might use.
* [Services](../services/README.md) - For complex, side-effecting helper infrastructure.
