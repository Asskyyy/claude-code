# Configuration Migrations (`/src/migrations`)

## 🎯 Purpose
This directory handles the logic for upgrading legacy configuration file formats on users' machines to newer schema versions defined in `/src/schemas`.

## 🏛️ Domain Boundaries
* **Owns:** Version-to-version migration scripts for configuration states.
* **Does NOT Own:** The base schema definitions (see `/src/schemas`).

## 🔑 Key Entry Files
* Migration logic runners.

## 🔄 Dependencies
* **Upstream (Depends on):** `/src/schemas`.
* **Downstream (Depended on by):** Application initialization logic (`/src/entrypoints`).

## 📖 Read Next
* [Schemas](../schemas/README.md)
