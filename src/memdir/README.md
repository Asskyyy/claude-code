# Memory Directory (`/src/memdir`)

## 🎯 Purpose
This directory manages the persistent, hierarchical memory of the agent, enabling the agent to recall context across sessions.

## 🏛️ Domain Boundaries
* **Owns:** Reading/writing to the local memory directory, managing memory schemas, and syncing memory across the team.
* **Does NOT Own:** The ephemeral, in-memory conversational history of the current session.

## 🔑 Key Entry Files
* Memory sync and extraction utilities.

## 🔄 Dependencies
* **Upstream (Depends on):** File system operations.
* **Downstream (Depended on by):** `/src/context` and the agent memory tools.

## 📖 Read Next
* [Context](../context/README.md)
