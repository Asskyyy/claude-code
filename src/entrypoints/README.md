# Entrypoints (`/src/entrypoints`)

## 🎯 Purpose
This directory contains the initial initialization logic and bootstrapping sequences for the CLI application.

## 🏛️ Domain Boundaries
* **Owns:** Bootstrapping the runtime environment, initial dependency injection, reading environment variables, and kicking off the primary execution loops.
* **Does NOT Own:** The command parsing logic (see `/src/cli`) or the tool execution loop itself (see `/src/query`).

## 🔑 Key Entry Files
* `index.ts` (if exists) or similar initializers - Starts the application.

## 🔄 Dependencies
* **Upstream (Depends on):** Node/Bun environment, `process.argv`.
* **Downstream (Depended on by):** The core `main.tsx` executable.

## 📖 Read Next
* [CLI Parsing](../cli/README.md)
* [Core Source Code](../README.md)
