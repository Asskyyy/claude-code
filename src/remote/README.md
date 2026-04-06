# Remote Sessions (`/src/remote`)

## Purpose
This directory contains the client-side networking and synchronization logic required to connect a local Claude Code terminal session to a remotely hosted daemon.

## Where this fits in the external integration architecture
This is the **Client Side** of a remote execution architecture. When a user runs a command to connect to a remote box (e.g., `/resume` or `/desktop`), this subsystem handles the connection and state synchronization.

## Owns
* Connecting to remote host endpoints.
* Synchronizing local terminal inputs and UI state with the remote server.
* Handling connection drops, retries, and session restoration.

## Does Not Own
* **The Server Implementation:** The actual daemon that this client connects to lives in `/src/server`.
* **IDE Bridge Logic:** The specific bidirectional sync for editors lives in `/src/bridge`.
* **User-Facing Slash Commands:** While commands like `/resume` trigger this logic, the command parsing itself lives in `/src/commands`.

## External boundary / protocol boundary
This subsystem faces **Remote Claude Code Servers**. The boundary is the network connection out to the server's API or socket.

## Key files / Key subpaths
* Remote session connection handlers.
* State synchronization utilities.

## Typical dependency direction
* **Depends on:** Networking APIs, serialization, and `/src/server` API contracts.
* **Depended on by:** Specific slash commands or CLI flags that initiate remote modes.

## How to read this folder
Look at how a connection is established and how the local terminal UI is bound to the incoming stream of data from the remote server.

## Read Next
* [Server Mode](../server/README.md) - To understand the host that this client connects to.
* [Slash Commands](../commands/README.md) - To see how users trigger remote sessions.
