# Type Definitions (`/src/types`)

## Purpose
This directory houses the shared TypeScript interfaces, utility types, and abstract type declarations used across the Claude Code codebase.

## Where this fits in the runtime / foundation architecture
This is a **compile-time only** surface. It defines the structural contracts that different subsystems (like the Query Engine, UI Components, or Services) use to communicate, without introducing any runtime behavior or execution overhead.

## Owns
* Global TypeScript `interface` and `type` definitions.
* Cross-module structural contracts.
* Highly reusable utility types (e.g., specific generic manipulations).

## Does Not Own
* **Runtime Validation:** Checking if actual data matches these types at runtime is the job of Zod schemas (see `/src/schemas`).
* **Runtime Values:** Actual hardcoded strings, numbers, or enums belong in `/src/constants`.
* **Domain Implementation:** Subsystem-specific types that are only used internally by one folder should stay within that folder, not here.

## Boundary with adjacent foundation layers
* **Vs. Schemas:** `types` exist only for the TypeScript compiler. `schemas` exist at runtime to validate incoming or stored data. Often, a `type` is inferred from a `schema`.
* **Vs. Constants:** `types` define what shape a value *can* take; `constants` provide the actual value.

## Key files / Key subpaths
* Shared type definition files (e.g., core system models, standardized API response shapes).

## Typical dependency direction
* **Depends on:** Nothing (pure TypeScript).
* **Depended on by:** The entire codebase. This is typically at the very bottom of the dependency graph.

## How to read this folder
Use this directory as a dictionary to understand the fundamental data structures of the application. If you see an unfamiliar type passed between the Query Engine and the UI, its definition is likely here.

## Read Next
* [Configuration Schemas](../schemas/README.md) - To see how these types are enforced at runtime.
* [Constants](../constants/README.md) - To see the actual values that satisfy these types.
