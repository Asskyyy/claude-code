# Query Engine (`/src/query`)

## Purpose
This directory houses the core execution engine responsible for managing LLM interactions, turn-based conversation flow, and context budgets.

## Where this fits in the pipeline
This is the "brain" of the execution path. After being initialized by an entrypoint, the Query Engine takes user input, communicates with the Anthropic API, decides when to invoke tools, and handles the state machine of a conversational turn.

## Owns
* Turn execution and model interaction.
* Context window and token budgeting.
* Execution interruption (stop hooks) and state machine transitions.

## Does Not Own
* The actual implementation of agent tools (see `/src/tools`).
* User-facing slash commands (see `/src/commands`).
* Persistent UI state or disk storage.

## Key files / Key subpaths
* `config.ts` - Core configurations for the query loop.
* `deps.ts` - Dependency injection wiring for the engine.
* `stopHooks.ts` - Logic for interrupting or pausing execution.
* `tokenBudget.ts` - Management of the LLM context window and token limits.
* `transitions.ts` - State machine definitions for moving between prompt generation, tool execution, and completion.

## Typical data / control flow
User Prompt → Token Budget Check → Anthropic API Request → Transition (e.g., `tool_calls` detected) → Tool Invocation → Stop Hook Check → Yield Response to UI.

## Read Next
* [Agent Tools](../tools/README.md)
* [Slash Commands](../commands/README.md)
