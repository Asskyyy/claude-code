# Utilities (`/src/utils`)

## 🎯 Purpose
This directory contains pure, stateless helper functions that are highly reusable and domain-agnostic.

## 🏛️ Domain Boundaries
* **Owns:** String manipulation, basic file path helpers, math utilities, and data structure transformers.
* **Does NOT Own:** Anything with side-effects, API calls, stateful logic, or domain-specific business rules. (Do NOT treat this as a dumping ground).

## 🔑 Key Entry Files
* Pure utility functions.

## 🔄 Dependencies
* **Upstream (Depends on):** Node/Bun built-ins.
* **Downstream (Depended on by):** Broadly across the app.

## 📖 Read Next
* [Core Source Code](../README.md)
