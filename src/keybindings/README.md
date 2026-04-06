# Keybindings (`/src/keybindings`)

## 🎯 Purpose
This directory handles raw terminal input events and maps them to application commands, enabling keyboard shortcuts within the interactive REPL.

## 🏛️ Domain Boundaries
* **Owns:** Parsing keypresses, shortcut definitions, and input event routing.
* **Does NOT Own:** The logic executed by the shortcuts (see `/src/commands` or component local state).

## 🔑 Key Entry Files
* Configuration for global shortcuts and key interceptors.

## 🔄 Dependencies
* **Upstream (Depends on):** Ink input handling, Node `readline`.
* **Downstream (Depended on by):** The REPL screen (`/src/screens`).

## 📖 Read Next
* [Screens](../screens/README.md)
