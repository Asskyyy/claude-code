# Configuration Schemas (`/src/schemas`)

## Purpose
This directory defines the runtime validation contracts and configuration shapes for Claude Code, acting as the definitive source of truth for structural integrity at runtime.

## Where this fits in the runtime / foundation architecture
This is the **runtime enforcement layer** for data structures. While `/src/types` only exist during compilation, schemas (typically powered by Zod) actively validate user settings, external API responses, and internal state shapes while the application is running.

## Owns
* Zod schema definitions for global user settings and project configurations.
* Runtime validation rules (e.g., minimum values, required fields, string formats).
* Derivation of TypeScript types from these runtime schemas.

## Does Not Own
* **Compile-time only abstract types:** Pure interfaces belong in `/src/types`.
* **Configuration Evolution:** Upgrading old configuration files to match the current schemas is handled by `/src/migrations`.
* **State Management:** Schemas define the *shape* of the state, but the actual state orchestration lives in `/src/state`.

## Boundary with adjacent foundation layers
* **Vs. Types:** Schemas provide active parsing and validation; types provide passive type-checking.
* **Vs. Migrations:** Schemas define the *current* valid state. Migrations handle the transition from *past* states.

## Key files / Key subpaths
* Schema definitions for various config files (e.g., global settings, project-level rules).

## Typical dependency direction
* **Depends on:** `zod` and potentially `/src/constants` (for allowed enum values).
* **Depended on by:** `/src/state`, `/src/services`, `/src/entrypoints` (during startup validation), and `/src/migrations`.

## How to read this folder
Look here to understand exactly what configuration options Claude Code accepts, what default values are applied, and what validation rules are enforced on those inputs.

## Read Next
* [Migrations](../migrations/README.md) - To see how legacy configs are updated to match these schemas.
* [Type Definitions](../types/README.md) - To understand the pure compile-time types.
