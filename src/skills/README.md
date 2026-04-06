# Agent Skills (`/src/skills`)

## 🎯 Purpose
This directory contains reusable, composable workflows and specialized instructions (skills) that augment the agent's baseline capabilities.

## 🏛️ Domain Boundaries
* **Owns:** Definition of skill schemas, loading logic for user-defined `.gemini/skills/` (or `.claude`), and the built-in default skills.
* **Does NOT Own:** The underlying execution engine that runs the skills (see `/src/query`), or the multi-agent coordination (see `/src/coordinator`).

## 🔑 Key Entry Files
* Skill parsing and validation logic.

## 🔄 Dependencies
* **Upstream (Depends on):** Local file system (for reading `.md` skill files), schema validators.
* **Downstream (Depended on by):** Agent Context and tool invocations.

## 📖 Read Next
* [Coordinator](../coordinator/README.md)
* [Tasks](../tasks/README.md)
