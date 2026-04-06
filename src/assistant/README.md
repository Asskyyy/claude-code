# Assistant Logic (`/src/assistant`)

## 🎯 Purpose
This directory contains specialized prompt structures and conversational management for the core assistant personality.

## 🏛️ Domain Boundaries
* **Owns:** `sessionHistory.ts` and core conversation formatting.
* **Does NOT Own:** The tool execution logic itself (see `/src/query`).

## 🔑 Key Entry Files
* `sessionHistory.ts`

## 🔄 Dependencies
* **Upstream (Depends on):** `/src/query`.
* **Downstream (Depended on by):** Query generation logic.

## 📖 Read Next
* [Query Engine](../query/README.md)
