# More Right Subsystem (`/src/moreright`)

## 🎯 Purpose
This directory contains specialized evaluation or alignment subsystems, handling logic to ensure the agent's behavior stays within safe/aligned bounds.

## 🏛️ Domain Boundaries
* **Owns:** Evaluation routines, alignment enforcement checks.
* **Does NOT Own:** General telemetry or base models.

## 🔑 Key Entry Files
* Core subsystem routines.

## 🔄 Dependencies
* **Upstream (Depends on):** The executed outputs.
* **Downstream (Depended on by):** `QueryEngine`.

## 📖 Read Next
* [Query Engine](../query/README.md)
