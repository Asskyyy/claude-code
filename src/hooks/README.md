# React Hooks (`/src/hooks`)

## 🎯 Purpose
This directory houses custom React hooks used across the terminal UI to encapsulate state logic, side-effects, and subscription to the global application state.

## 🏛️ Domain Boundaries
* **Owns:** Logic for accessing permissions, IDE integration state, session info, and component-level lifecycle management.
* **Does NOT Own:** The definition of the global state itself (see `/src/state`).

## 🔑 Key Entry Files
* Hooks for tool permission checks, UI themes, and reactive state reading.

## 🔄 Dependencies
* **Upstream (Depends on):** React, `/src/state`, and `/src/context`.
* **Downstream (Depended on by):** UI Components (`/src/components`) and Screens (`/src/screens`).

## 📖 Read Next
* [State Management](../state/README.md)
* [Context](../context/README.md)
