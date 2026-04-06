# UI Components (`/src/components`)

## 🎯 Purpose
This directory contains the React components used to render the terminal UI using the Ink framework.

## 🏛️ Domain Boundaries
* **Owns:** Presentation layer components, styling logic, layout constructs, and interactive terminal elements (e.g., text inputs, spinners).
* **Does NOT Own:** Direct calls to the LLM Query Engine (see `/src/query`), or global application state mutations (see `/src/state`).

## 🔑 Key Entry Files
* Various common components used throughout the CLI interface.

## 🔄 Dependencies
* **Upstream (Depends on):** `ink` (React for CLI), `/src/hooks` for accessing state, and `/src/context`.
* **Downstream (Depended on by):** `/src/screens` which compose these into full views.

## 📖 Read Next
* [Screens](../screens/README.md)
* [Ink Integrations](../ink/README.md)
