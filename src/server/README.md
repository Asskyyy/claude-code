# Server Mode (`/src/server`)

## 🎯 Purpose
This directory provides the infrastructure for the CLI to run as a persistent daemon or remote server, allowing remote sessions to connect to it.

## 🏛️ Domain Boundaries
* **Owns:** Server lifecycle, port binding, and hosting the CLI engine for remote clients.
* **Does NOT Own:** External user authentication services, or specific IDE transport layers (see `/src/bridge`).

## 🔑 Key Entry Files
* Core server initialization and request handling logic.

## 🔄 Dependencies
* **Upstream (Depends on):** Node/Bun networking APIs.
* **Downstream (Depended on by):** Remote clients.

## 📖 Read Next
* [Remote Sessions](../remote/README.md)
