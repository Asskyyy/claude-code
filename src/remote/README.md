# Remote Sessions (`/src/remote`)

## 🎯 Purpose
This directory contains the client-side and synchronization logic for connecting a local CLI session to a remotely hosted agent daemon.

## 🏛️ Domain Boundaries
* **Owns:** Connecting to remote hosts, syncing session state, and forwarding terminal inputs.
* **Does NOT Own:** The implementation of the remote daemon itself (see `/src/server`).

## 🔑 Key Entry Files
* Remote session connection handlers.

## 🔄 Dependencies
* **Upstream (Depends on):** Networking APIs and `/src/server` endpoints.
* **Downstream (Depended on by):** Commands like `/resume` or `/desktop`.

## 📖 Read Next
* [Server Mode](../server/README.md)
