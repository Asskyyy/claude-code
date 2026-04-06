# Query Engine (`/src/query`)

## 🎯 Purpose
This directory houses the core LLM execution loop, responsible for interacting with Anthropic APIs, managing conversational state, and dispatching tool calls.

## 🏛️ Domain Boundaries
* **Owns:** API request/response parsing, the tool execution loop, prompt injection logic, and raw context handling.
* **Does NOT Own:** Tool implementation details (see `/src/tools`), user UI (see `/src/components`), or local state persistence (see `/src/state`).

## 🔑 Key Entry Files
* `QueryEngine.ts` (often placed here or references this subsystem) - The main loop calling the Claude API.
* Token and cost estimation functions related to queries.

## 🔄 Dependencies
* **Upstream (Depends on):** `/src/tools`, Anthropic SDK.
* **Downstream (Depended on by):** The interactive CLI REPL and terminal UI.

## 📖 Read Next
* [Tools](../tools/README.md)
* [Terminal UI](../components/README.md)
