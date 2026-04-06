# Slash Commands (`/src/commands`)

## Purpose
This directory implements the user-facing slash command system, allowing human users to interact directly with the Claude Code REPL using `/` prefixes (e.g., `/commit`, `/review`).

## Where this fits in the pipeline
Slash commands act as direct user interventions that run *outside* or *parallel to* the standard LLM query loop. They are intercepted by the input parser before reaching the main prompt generation sequence.

## Owns
* User-facing command definitions and argument parsing.
* Immediate terminal feedback and interactive prompts for specific commands.
* Direct mutation of session state or context via commands.

## Does Not Own
* Agent capabilities invoked by the model (see `/src/tools`).
* The core conversational execution loop (see `/src/query`).
* The baseline UI input components.

## Key files / Key subpaths
Commands are conceptually grouped into administrative and workflow functions:
* **Session & Context:** Modifying what the model sees (e.g., `/compact`, `/context`, `/memory`).
* **Workflow & Automation:** Triggering high-level routines (e.g., `/commit`, `/review`, `/pr_comments`).
* **Configuration & Environment:** Adjusting settings (e.g., `/config`, `/theme`, `/vim`).
* **Diagnostics:** Health checks and metrics (e.g., `/doctor`, `/cost`).

## Typical data / control flow
User types `/command [args]` in REPL → Parser intercepts input → Command logic executes locally → Feedback is rendered directly to the terminal UI without invoking the LLM (unless the command explicitly requires it).

## Read Next
* [Commands Reference](../../docs/commands.md)
* [UI Components](../components/README.md)
