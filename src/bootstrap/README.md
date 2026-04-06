# Application Bootstrap (`/src/bootstrap`)

## 🎯 Purpose
This directory manages the initial setup and dependency wiring required before the main UI and execution loops can safely start.

## 🏛️ Domain Boundaries
* **Owns:** Pre-flight checks, logger setup, crash handler initialization, and initial dependency injection.
* **Does NOT Own:** Command-line argument parsing (see `/src/cli`).

## 🔑 Key Entry Files
* Bootstrap sequence logic.

## 🔄 Dependencies
* **Upstream (Depends on):** Core node services.
* **Downstream (Depended on by):** Application entrypoints (`/src/entrypoints`).

## 📖 Read Next
* [Entrypoints](../entrypoints/README.md)
