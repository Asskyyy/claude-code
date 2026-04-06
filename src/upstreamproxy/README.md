# Upstream Proxy (`/src/upstreamproxy`)

## 🎯 Purpose
This directory configures and manages the routing of outbound HTTP/API requests through custom corporate or developer proxies.

## 🏛️ Domain Boundaries
* **Owns:** Proxy auto-configuration reading (PAC), HTTPS proxy agent setup, and handling proxy authentication.
* **Does NOT Own:** The actual API clients making the requests (see `/src/services`).

## 🔑 Key Entry Files
* Proxy agent builders and environment variable parsers.

## 🔄 Dependencies
* **Upstream (Depends on):** Environment variables (`HTTP_PROXY`, etc.).
* **Downstream (Depended on by):** All outbound network calls across the application.

## 📖 Read Next
* [Services](../services/README.md)
