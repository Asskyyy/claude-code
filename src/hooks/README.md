# React Hooks (`/src/hooks`)

## Purpose
This directory houses custom React hooks that encapsulate complex UI-side behaviors, state subscriptions, and side-effects, making them easily reusable across different terminal components.

## Where this fits in the UI/runtime architecture
Hooks act as the "nervous system" of the UI layer. They sit between the Context/State layer and the visual Components layer. Instead of components directly managing raw subscriptions or complex logic, they call a hook.

## Owns
* **State Access:** Subscribing components to specific slices of the global `/src/state`.
* **Permissions:** Hooks for requesting and validating tool execution permissions from the user.
* **Input Handling:** Managing terminal keystrokes and prompt history.
* **Integrations:** Wrapping IDE bridge events or external notifications into React state.
* **Component Lifecycle:** Managing specific UI side-effects (timers, focus management).

## Does Not Own
* The source of truth for global state (see `/src/state`).
* The visual rendering of the terminal UI (see `/src/components`).
* The actual execution of system commands or tools.

## Key files / Key subpaths
Hooks are conceptually grouped by the domains they manage:
* `toolPermission/` - Logic for prompting the user for approval/denial based on the current permission mode.
* Input and Session hooks - Managing the active REPL prompt and session history.
* IDE/Plugin hooks - Subscribing to events from the `/src/bridge` or `/src/plugins`.

## Typical dependency direction
* **Depends on:** React, `/src/context` (to access providers), and `/src/state` (for subscriptions).
* **Depended on by:** `/src/components` and `/src/screens` (which use these hooks to drive their rendering).

## How to read this folder
If you want to know *how* a component knows it's time to ask for permission, or *how* it receives text input, look here. Understand hooks as the behavioral logic blocks that power the dumb visual components.

## Read Next
* [Components](../components/README.md) - To see where these hooks are actually used to render UI.
* [Context](../context/README.md) - To understand where the hooks get their underlying data.
