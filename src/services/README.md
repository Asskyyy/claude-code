# Services (`/src/services`)

## Purpose
This directory contains external integrations, singleton-style runtime infrastructure, and side-effecting adapters that provide foundational capabilities to Claude Code.

## Where this fits in the runtime / foundation architecture
This is the **infrastructure and integration backbone**. It sits below the core execution loop (`/src/query`) and the UI (`/src/components`), providing the heavy-lifting capabilities required to interact with the outside world or manage complex global lifecycles.

## Owns
* **External API Adapters:** Clients for interacting with the Anthropic API, OAuth providers, etc.
* **Telemetry & Analytics:** Integrations for feature flags, crash reporting, and usage metrics.
* **Global Infrastructure:** Singletons for token estimation, policy limit enforcement, and context compression.
* **Side-effecting logic:** Anything requiring persistent network connections or complex file I/O coordination.

## Does Not Own
* **Agent Tools:** Services are low-level infrastructure. Agent Tools (`/src/tools`) are model-invoked capabilities that often *use* these services.
* **Pure Utilities:** Stateless formatting or math helpers belong in `/src/utils`.
* **UI Rendering:** Services operate completely independent of the React/Ink terminal interface.

## Boundary with adjacent foundation layers
* **Vs. Utils:** Services perform I/O, maintain persistent connections, or rely on global state. Utils are pure `f(x) -> y` functions.
* **Vs. Bootstrap:** The Bootstrap phase (`/src/bootstrap`) initializes these services; the Services themselves provide the ongoing capabilities.

## Key files / Key subpaths
* `api/` - Anthropic API clients and request management.
* `oauth/` - Authentication flows and token management.
* `analytics/` - Feature flags (e.g., GrowthBook) and telemetry infrastructure.

## Typical dependency direction
* **Depends on:** External network APIs, configuration (`/src/schemas`), and local OS capabilities.
* **Depended on by:** Almost all higher-level application modules, typically injected via React Context or imported as global singletons.

## How to read this folder
Look here to understand how Claude Code connects to external systems. If you need to trace how an API request is authenticated and dispatched, or how feature flags govern application behavior, the service layer is where that logic resides.

## Read Next
* [Agent Tools](../tools/README.md) - To see how these infrastructure services are utilized by the LLM.
* [React Context](../context/README.md) - To see how these services are injected into the UI.
* [Application Bootstrap](../bootstrap/README.md) - To see how these services are initialized on startup.
