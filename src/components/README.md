# UI Components (`/src/components`)

## Purpose
This directory contains the reusable React components used to render the terminal UI via the Ink framework.

## Where this fits in the UI/runtime architecture
This is the presentation layer. These components are the "dumb" visual building blocks of the application. They take data (via props or hooks) and render formatted text, colors, layouts, and interactive elements to the user's terminal.

## Owns
* Presentation logic and layout constructs.
* Reusable terminal UI primitives (e.g., specific text inputs, spinners, structured boxes, markdown renderers).
* Ink styling implementation (colors, padding, flexbox).

## Does Not Own
* Global state management (see `/src/state`).
* Full-screen orchestrations or high-level mode loops (see `/src/screens`).
* Complex business logic or direct interactions with the LLM Query Engine (components should use `/src/hooks` to trigger actions).

## Key files / Key subpaths
* Common layout primitives (Boxes, Spacers).
* Interactive elements (Inputs, Selectors).
* Feedback elements (Spinners, Progress bars, Error banners).

## Typical dependency direction
* **Depends on:** `ink` (React for CLI), `/src/outputStyles`, and `/src/hooks` (for data access and behavior).
* **Depended on by:** `/src/screens` (which compose these blocks into complete applications) and `/src/commands` (for rendering specific command output).

## How to read this folder
Treat this as the application's design system and UI library. If you need to render a new visual element, check here first for existing primitives. Do not look here for application control flow.

## Read Next
* [UI Screens](../screens/README.md) - To see how these components are assembled into full views like the REPL.
* [Hooks](../hooks/README.md) - To understand how these components get their interactive behavior.
