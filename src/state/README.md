# Global App State (`/src/state`)

## Purpose
This directory implements the core reactive state management system for the Claude Code runtime. It acts as the single, mutable source of truth for the interactive CLI session.

## Where this fits in the UI/runtime architecture
This is the foundational data layer for the application's runtime. It sits below the React tree. Both the core engine (`/src/query`) and the UI components (`/src/components` via `/src/hooks`) read from and mutate this global state.

## Owns
* The definition of the global `AppState` object.
* State mutation functions and reducers.
* Selectors and observer patterns (`onChangeAppState`) used to reactively push updates to subscribers without deep React prop-drilling.

## Does Not Own
* Persistent, disk-backed memory or long-term history (see `/src/memdir` and `/src/assistant/sessionHistory.ts`).
* React-specific subscription logic or lifecycle management (see `/src/hooks`).
* The UI rendering loop itself (see `/src/ink`).

## Key files / Key subpaths
* `state.ts` (or equivalent primary store file) - Defines the core `AppState` interface and the store instance.
* Selectors - Functions for deriving specific slices of state.
* Observers - Mechanisms for triggering side-effects when specific state nodes change.

## Typical dependency direction
* **Depends on:** Core models, configuration schemas (`/src/schemas`), and system types.
* **Depended on by:** `/src/hooks` (for UI reactivity), `/src/context` (for injection), and the CLI execution handlers.

## How to read this folder
Start by understanding the shape of the global store. Look at the primary state definition file to see what data the application holds in memory during a session. Then, review how selectors extract that data and how mutations are applied.

## Read Next
* [Context](../context/README.md) - To see how this state is provided to the React UI.
* [Hooks](../hooks/README.md) - To see how the UI subscribes to this state.
