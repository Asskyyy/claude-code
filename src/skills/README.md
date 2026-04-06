# Agent Skills (`/src/skills`)

## Purpose
This directory manages the "Skills" subsystem. Skills are reusable, higher-level workflow definitions and capability instructions that can be dynamically loaded to shape the agent's behavior for specific tasks.

## Where this fits in the architecture
Skills sit between the raw capabilities of Agent Tools (`/src/tools`) and the core execution loop (`/src/query`). While tools provide isolated actions (e.g., "run a bash command"), skills provide the *instructions* and *patterns* for using those tools effectively to achieve a broader goal.

## Owns
* **Capability Packaging:** Bundling specific instructions, prompts, and tool requirements into a cohesive unit.
* **Skill Discovery & Loading:** The logic to scan directories (like `.claude/skills/`), parse skill files, and register them.
* **Skill Construction:** Builders and utilities for translating raw skill definitions into formats the LLM or MCP can consume.

## Does Not Own
* **Execution Orchestration:** The `QueryEngine` (`/src/query`) decides *when* and *how* to apply a skill during a turn; the skill itself is just the definition.
* **Tool Implementations:** Skills might orchestrate tools, but the actual tool execution logic lives in `/src/tools`.
* **System Prompt Research:** Historical rationale or research notes for system prompts live in `/prompts/`.

## Authority / data boundary
Skills are part of the **instruction surface**. They inject specialized context and behavioral rules into the model's prompt when active. However, they are **lazily loaded** and selected based on need, rather than being permanently resident in the top-level system prompt, preserving the context window budget.

## Key files / Key subpaths
* **Bundled Skills:** Implementations of default, built-in skills shipped with the CLI.
* **Skill Loaders/Registries:** Logic responsible for finding and validating user-defined custom skills.
* **MCP Integration:** Builders that potentially wrap skills for exposure or consumption via the Model Context Protocol.

## How loading / discovery works
The system scans designated locations (e.g., the workspace's `.claude/skills/` directory) for skill definitions. These definitions are parsed, validated, and registered into a capability catalog. When the user requests a specific workflow, or the model determines a skill is relevant, the specific skill's instructions are retrieved and injected into the current context window.

## How to read this folder
Focus on understanding the lifecycle of a skill: how it is discovered on disk, how it is parsed into a structured capability, and the shape of the interface it exposes to the `QueryEngine` for invocation.

## Read Next
* [Query Engine](../query/README.md) - To see how these loaded skills are actually injected into the LLM's context.
* [Agent Tools](../tools/README.md) - To understand the raw capabilities that skills orchestrate.
* [Subsystems Overview](../../docs/subsystems.md) - For a broader architectural view of skills.
