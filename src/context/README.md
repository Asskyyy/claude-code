# React Context (`/src/context`)

## 🎯 Purpose
This directory provides React Context providers and consumers to cleanly inject dependencies (like API clients, config, and state) down the UI component tree without prop-drilling.

## 🏛️ Domain Boundaries
* **Owns:** Context definitions, Context Providers, and logic to bridge global instances into the React tree.
* **Does NOT Own:** The instantiated services themselves (see `/src/services`).

## 🔑 Key Entry Files
* Various context provider definitions.

## 🔄 Dependencies
* **Upstream (Depends on):** React, `/src/state`, `/src/services`.
* **Downstream (Depended on by):** Application roots (`main.tsx`) and components.

## 📖 Read Next
* [State Management](../state/README.md)
