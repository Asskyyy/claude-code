# React Context (`/src/context`)

## Purpose
This directory defines the React Context providers and consumers used to inject shared dependencies, global state, and runtime services down into the terminal UI component tree.

## Where this fits in the UI/runtime architecture
This layer acts as the bridge between the global, non-React application runtime (services, engines, global state) and the React-based presentation layer. It prevents deep prop-drilling across the UI.

## Owns
* React Context definitions (`React.createContext`).
* Context Provider components that wrap the application roots.
* Logic to bind external singleton instances (like API clients or the Query Engine) to the React lifecycle.

## Does Not Own
* The implementation of the services being provided (see `/src/services`).
* The definition of the global state object itself (see `/src/state`).
* The UI logic that consumes these contexts (see `/src/hooks` and `/src/components`).

## Key files / Key subpaths
* Provider components for theme, configuration, services, and core application state.

## Typical dependency direction
* **Depends on:** `/src/state`, `/src/services`, and React.
* **Depended on by:** The application roots (`main.tsx`, `/src/screens`) which render the providers, and `/src/hooks` which consume them.

## How to read this folder
Look at the Context Providers to understand the "environment" that the UI components run within. If a component needs access to the file system, the LLM engine, or global settings, it is likely injected through a provider defined here.

## Read Next
* [Hooks](../hooks/README.md) - To see how components easily consume these contexts.
* [State](../state/README.md) - To understand the data being injected.
