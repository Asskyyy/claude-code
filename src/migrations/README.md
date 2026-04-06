# Configuration Migrations (`/src/migrations`)

## Purpose
This directory handles the evolution of configuration formats, ensuring that legacy settings files on a user's machine are safely upgraded to the current schema structures.

## Where this fits in the runtime / foundation architecture
This is an **initialization-phase transition layer**. It sits between the raw, potentially outdated config file on disk and the strict runtime validation layer (`/src/schemas`). It ensures backward compatibility for users updating Claude Code.

## Owns
* Version-to-version migration scripts for configuration states.
* Logic to detect outdated configuration formats.
* Safe transformation of deprecated settings into their modern equivalents.

## Does Not Own
* **The Current Schema Definition:** The target "correct" shape is owned by `/src/schemas`.
* **General Startup Orchestration:** The overarching startup sequence that *calls* these migrations lives in `/src/entrypoints` or `/src/bootstrap`.
* **Runtime State Mutation:** Once migrated and loaded, active state changes happen in `/src/state`.

## Boundary with adjacent foundation layers
* **Vs. Schemas:** Migrations bridge the gap between historical data and current schemas. They only run when a mismatch is detected.
* **Vs. Bootstrap:** Bootstrap manages the *process* of starting up; migrations specifically manage the *data transformation* during that process.

## Key files / Key subpaths
* Migration logic runners and version-specific transform functions.

## Typical dependency direction
* **Depends on:** `/src/schemas` (the target shape) and file system utilities.
* **Depended on by:** Initialization logic in `/src/bootstrap` or `/src/entrypoints`.

## How to read this folder
If a user reports that an old setting is no longer working after an update, check the migration scripts here to see how that legacy setting is being translated into the current configuration shape.

## Read Next
* [Configuration Schemas](../schemas/README.md) - To see the final schema that these migrations target.
* [Application Bootstrap](../bootstrap/README.md) - To see when these migrations are triggered.
