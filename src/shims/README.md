# Runtime Shims (`/src/shims`)

## 🎯 Purpose
This directory provides polyfills and shims to normalize behavior across different runtimes (Node.js vs. Bun).

## 🏛️ Domain Boundaries
* **Owns:** API polyfills and environment normalization patches.
* **Does NOT Own:** The core business logic.

## 🔑 Key Entry Files
* Various shim definitions.

## 🔄 Dependencies
* **Upstream (Depends on):** Node APIs.
* **Downstream (Depended on by):** Global runtime environment.

## 📖 Read Next
* [Bootstrap](../bootstrap/README.md)
