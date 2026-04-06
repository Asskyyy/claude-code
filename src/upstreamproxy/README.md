# Upstream Proxy (`/src/upstreamproxy`)

## Purpose
This directory manages the configuration and routing of outbound HTTP and API requests through custom corporate or developer proxies.

## Where this fits in the external integration architecture
This is a **cross-cutting infrastructure layer**. It sits below the service clients (like the Anthropic API client) and ensures that all outbound network traffic respects the user's local network proxy settings.

## Owns
* Reading and parsing proxy environment variables (`HTTP_PROXY`, `HTTPS_PROXY`, `NO_PROXY`).
* Proxy Auto-Configuration (PAC) file reading and evaluation.
* Setup of custom Node/Bun HTTPS proxy agents.
* Handling proxy authentication credentials.

## Does Not Own
* **Actual API Clients:** This directory only configures the *transport*; the actual clients making requests to Anthropic or other services live in `/src/services`.
* **Integration Logic:** This is not a feature surface (like Plugins or the IDE Bridge); it is pure network routing plumbing.

## External boundary / protocol boundary
This subsystem faces **Local Network Proxies**. The boundary is the standard HTTP/HTTPS proxy protocols (CONNECT, etc.) and PAC file standards.

## Key files / Key subpaths
* Proxy agent builder functions.
* Environment variable and PAC file parsers.

## Typical dependency direction
* **Depends on:** Node/Bun networking internals (`http`, `https`, `tls`) and environment variables.
* **Depended on by:** Almost all outbound network calls across the application (typically injected into `/src/services`).

## How to read this folder
Understand this as a utility for generating `Agent` objects that can be passed to `fetch()` or external SDKs to route traffic correctly.

## Read Next
* [Services](../services/README.md) - To see where these proxy agents are actually used to make API calls.
