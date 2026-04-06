# Multi-Agent Coordinator (`/src/coordinator`)

## 🎯 Purpose
This directory orchestrates complex multi-agent workflows, managing team assignments, communication, and goal synthesis across multiple spawned sub-agents.

## 🏛️ Domain Boundaries
* **Owns:** Orchestration logic, message routing between agents, and multi-agent state machines.
* **Does NOT Own:** The implementation of individual skills (see `/src/skills`), or basic parallel background processes (see `/src/tasks`).

## 🔑 Key Entry Files
* Core orchestration loop components.

## 🔄 Dependencies
* **Upstream (Depends on):** The primary `QueryEngine` to spawn instances.
* **Downstream (Depended on by):** Team management tools.

## 📖 Read Next
* [Tasks](../tasks/README.md)
