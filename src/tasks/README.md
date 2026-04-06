# Task Management (`/src/tasks`)

## 🎯 Purpose
This directory handles the creation, state management, and execution lifecycle of background or parallel tasks that the agent can spawn.

## 🏛️ Domain Boundaries
* **Owns:** Task definitions, status tracking, and the API for the agent to delegate work.
* **Does NOT Own:** The complex inter-agent communication protocols (see `/src/coordinator`).

## 🔑 Key Entry Files
* `Task.ts` / `tasks.ts` - Core definitions for managing parallel work.

## 🔄 Dependencies
* **Upstream (Depends on):** Core models and state.
* **Downstream (Depended on by):** Agent tools (`TaskCreateTool`, `TaskUpdateTool`).

## 📖 Read Next
* [Coordinator](../coordinator/README.md)
* [Tools](../tools/README.md)
