# Ink Integration (`/src/ink`)

## 🎯 Purpose
This directory contains wrappers and utilities for integrating with the `ink` rendering engine, managing terminal output streams, and handling stdout/stderr capturing cleanly.

## 🏛️ Domain Boundaries
* **Owns:** Render loop management, terminal measurement hooks, and graceful degradation for non-interactive environments.
* **Does NOT Own:** Business logic of the UI components (see `/src/components`).

## 🔑 Key Entry Files
* `ink.ts` - Setup and teardown functions for the Ink render instance.

## 🔄 Dependencies
* **Upstream (Depends on):** `ink` library, Node.js `process.stdout`/`stdin`.
* **Downstream (Depended on by):** `main.tsx` and core CLI handlers.

## 📖 Read Next
* [Components](../components/README.md)
