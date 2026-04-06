# Companion Sprite (`/src/buddy`)

## 🎯 Purpose
This directory handles the UI logic and rendering for the optional "Buddy" companion sprite (Easter egg 🐣) in the terminal interface.

## 🏛️ Domain Boundaries
* **Owns:** Sprite animation frames, companion notification hooks, and rendering logic.
* **Does NOT Own:** Core terminal UI components (see `/src/components`).

## 🔑 Key Entry Files
* `CompanionSprite.tsx`, `useBuddyNotification.tsx`.

## 🔄 Dependencies
* **Upstream (Depends on):** Ink framework, UI state.
* **Downstream (Depended on by):** `/src/screens`.

## 📖 Read Next
* [UI Screens](../screens/README.md)
