# Services (`/src/services`)

## 🎯 Purpose
This directory contains external integrations, core infrastructure components, and singletons that provide foundational capabilities to the application.

## 🏛️ Domain Boundaries
* **Owns:** API clients (Anthropic API), telemetry, feature flags, global token tracking, auth logic, and external system adapters.
* **Does NOT Own:** Interactive UI components (see `/src/components`), or specific tool logic (see `/src/tools`).

## 🔑 Key Entry Files
* Subdirectories like `api/`, `oauth/`, `analytics/`.

## 🔄 Dependencies
* **Upstream (Depends on):** External network APIs, configuration.
* **Downstream (Depended on by):** Almost all other system modules (injected via Context or used globally).

## 📖 Read Next
* [Core Source Code](../README.md)
