# State Management (`/src/state`)

## 🎯 Purpose
This directory implements the core reactive state management system (e.g., `AppState`, observers) that acts as the single source of truth for the interactive CLI session.

## 🏛️ Domain Boundaries
* **Owns:** Global state objects, state mutation functions, and the observer/selector patterns used to reactively update the UI.
* **Does NOT Own:** React-specific implementation details (see `/src/hooks`) or persistent disk memory (see `/src/memdir`).

## 🔑 Key Entry Files
* `state.ts` (or similar) - Defines the core `AppState` object.

## 🔄 Dependencies
* **Upstream (Depends on):** Core models and configuration schemas.
* **Downstream (Depended on by):** `/src/hooks` and CLI initialization.

## 📖 Read Next
* [Hooks](../hooks/README.md)
* [Memory Directory](../memdir/README.md)
