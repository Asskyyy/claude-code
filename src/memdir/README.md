# Memory Directory (`/src/memdir`)

## Purpose
This directory implements the persistent memory subsystem. It handles the storage, scanning, selection, and retrieval of long-term context that spans across multiple CLI sessions.

## Where this fits in the architecture
This is the **persistent retrieval surface**. When the `QueryEngine` (`/src/query`) needs historical context or project-specific knowledge that isn't part of the immediate conversational turn, it requests relevant context from this subsystem.

## Owns
* **Persistent Storage:** Reading from and writing to the local disk-backed memory directory (e.g., parsing `.md` memory files).
* **Memory Scanning & Selection:** Logic for determining which pieces of persistent memory are most relevant to the current task or query.
* **Memory Typing:** Defining the schemas and structures for different categories of saved knowledge.

## Does Not Own
* **Runtime App State:** The immediate, ephemeral state of the UI or the current CLI session (see `/src/state`).
* **Conversational History:** The short-term history of the current chat session (see `sessionHistory.ts` in `/src/assistant`).
* **Prompt Engineering Notes:** The project's own internal documentation and rationale (see `/prompts/`).

## Authority / data boundary
`memdir` is a **data provider**, not a policy engine. It retrieves and ranks relevant context, but it relies on the `QueryEngine` to decide how (or if) to inject that context into the LLM's prompt. It is distinct from `skills` in that it provides *knowledge* rather than *behavioral instructions*.

## Key files / Key subpaths
* **Core Memdir Module:** The primary classes/functions for interacting with the on-disk memory structure.
* **Relevance / Scanning Logic:** Algorithms for filtering a large set of memory files down to the most applicable subset for the current context budget.
* **Integration Files:** Glue code for syncing team memory or injecting retrieved memory into the active prompt structure.

## How loading / discovery works
Unlike the active conversational history which is held in memory, `memdir` reads from persistent storage. When a query is initiated, the subsystem scans the available memory artifacts, evaluates their relevance to the current context, and returns a prioritized list of knowledge snippets to be considered for inclusion by the query pipeline.

## How to read this folder
Start by looking at how memory files are represented as types. Then, trace the path of a "scan" or "retrieval" request to understand how the system decides what persistent knowledge is relevant enough to pull into the active session.

## Read Next
* [Query Engine](../query/README.md) - To see how retrieved memory is injected into the context window.
* [Global App State](../state/README.md) - To understand the difference between this persistent memory and ephemeral session state.
* [Subsystems Overview](../../docs/subsystems.md) - For a broader architectural view of memory.
