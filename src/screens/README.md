# UI Screens (`/src/screens`)

## 🎯 Purpose
This directory contains the high-level, full-terminal view components that orchestrate multiple UI components to represent distinct interactive modes (e.g., REPL, Doctor, Resume).

## 🏛️ Domain Boundaries
* **Owns:** Full-screen layouts, composition of smaller components, and high-level interaction loops for specific modes.
* **Does NOT Own:** Reusable, small-scale UI elements (see `/src/components`).

## 🔑 Key Entry Files
* e.g., `replLauncher.tsx`, `DoctorScreen.tsx` - Full view orchestrators.

## 🔄 Dependencies
* **Upstream (Depends on):** `/src/components`, `/src/hooks`, and `/src/state`.
* **Downstream (Depended on by):** CLI handlers (`/src/cli`) and `main.tsx`.

## 📖 Read Next
* [Components](../components/README.md)
