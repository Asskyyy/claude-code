# IDE Bridge (`/src/bridge`)

## 🎯 Purpose
This directory implements a bidirectional communication layer connecting the CLI application with external IDE extensions (like VS Code or JetBrains).

## 🏛️ Domain Boundaries
* **Owns:** The communication protocol (messaging), authorization checks for remote IDEs, and forwarding IDE requests into the CLI environment.
* **Does NOT Own:** Standalone local plugins (see `/src/plugins`), or general MCP server integrations.

## 🔑 Key Entry Files
* `bridgeMain.ts` - The primary initialization loop for the bridge.
* `bridgeMessaging.ts` - Definition of the communication protocol.

## 🔄 Dependencies
* **Upstream (Depends on):** Local sockets / secure transports.
* **Downstream (Depended on by):** External IDE extensions that connect to this instance.

## 📖 Read Next
* [Subsystems Overview](../../docs/subsystems.md)
