# Configuration Schemas (`/src/schemas`)

## 🎯 Purpose
This directory defines the single source of truth for the application's configuration shape, typically using Zod for runtime validation.

## 🏛️ Domain Boundaries
* **Owns:** Zod schema definitions for global user settings, project configs, and internal state shapes.
* **Does NOT Own:** The actual instantiation or migration of these configurations.

## 🔑 Key Entry Files
* Schema definitions for various config files.

## 🔄 Dependencies
* **Upstream (Depends on):** `zod`.
* **Downstream (Depended on by):** `/src/state`, `/src/services`, and `/src/migrations/`.

## 📖 Read Next
* [Migrations](../migrations/README.md)
