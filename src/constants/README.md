# Constants (`/src/constants`)

## Purpose
This directory centralizes global, hardcoded runtime values used consistently across the Claude Code application to prevent "magic strings" and "magic numbers."

## Where this fits in the runtime / foundation architecture
This is a **static value repository**. It provides named, reusable values that guide logic across the entire application, ensuring consistency without introducing side-effects or state.

## Owns
* Global symbolic names, enums, and string literals.
* Default configuration limits (e.g., max token counts, timeout durations).
* Hardcoded URL endpoints and environment variable keys.

## Does Not Own
* **Dynamic State:** Values that change during a session belong in `/src/state`.
* **Helper Logic:** Functions that compute or format values belong in `/src/utils`.
* **Structural Definitions:** The shape of data belongs in `/src/types` or `/src/schemas`.

## Boundary with adjacent foundation layers
* **Vs. Types:** Constants provide concrete runtime *values*; types provide abstract compile-time *shapes*.
* **Vs. Utils:** Constants are pure data; utils are pure functions.

## Key files / Key subpaths
* Shared constant exports grouped by domain (e.g., network constants, UI constants).

## Typical dependency direction
* **Depends on:** Nothing.
* **Depended on by:** Broadly across the entire application (Services, Components, Query Engine, etc.).

## How to read this folder
Treat this as the application's configuration baseline. If you need to change a default timeout, a standard message string, or an API endpoint, you should look for its definition here rather than hunting through execution logic.

## Read Next
* [Type Definitions](../types/README.md) - To see how these constants might be used in type unions or interfaces.
* [Utilities](../utils/README.md) - For stateless functions that might operate on these constants.
