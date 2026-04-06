# Application Bootstrap (`/src/bootstrap`)

## Purpose
This directory manages the critical pre-flight checks, logger setup, and initial dependency wiring required *before* the main Claude Code UI or execution loops can safely commence.

## Where this fits in the runtime / foundation architecture
This is the **startup sequence orchestrator**. It runs immediately after the process is launched (via `/src/entrypoints`), but before the primary application logic takes over. It ensures the environment is safe and ready.

## Owns
* Pre-flight environment checks (e.g., validating Node/Bun versions).
* Initialization of global error handlers and loggers.
* The initial wiring and instantiation of critical foundation services.

## Does Not Own
* **Process Entry:** The actual CLI argument parsing and mode routing happens in `/src/entrypoints`.
* **Long-lived Services:** Bootstrap sets up the services (`/src/services`), but the services themselves own their ongoing runtime logic.
* **Configuration Migration:** Upgrading old configs is handled by `/src/migrations`, though bootstrap might trigger that process.

## Boundary with adjacent foundation layers
* **Vs. Entrypoints:** Entrypoints parse the user's intent from the shell. Bootstrap prepares the internal engine to fulfill that intent.
* **Vs. Services:** Bootstrap wires the services together; it doesn't implement the service logic.

## Key files / Key subpaths
* Core initialization sequences and crash handler setups.

## Typical dependency direction
* **Depends on:** Core node services, `/src/services`, and `/src/schemas` (for initial validation).
* **Depended on by:** Application entrypoints (`/src/entrypoints`).

## How to read this folder
Read this to understand the "boot sequence" of the application. If you need to add a check that must pass before the UI renders, or initialize a global telemetry provider immediately on startup, it belongs here.

## Read Next
* [Entrypoints](../entrypoints/README.md) - To see what triggers the bootstrap sequence.
* [Services](../services/README.md) - To see the infrastructure that the bootstrap sequence initializes.
