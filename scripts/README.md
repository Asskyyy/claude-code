# Scripts & Tooling (`/scripts`)

## 🎯 Purpose
This directory contains utility scripts, build processes, testing harnesses, and CI/CD automation tools used to manage the lifecycle of the Gemini CLI project.

## 🏛️ Domain Boundaries
* **Owns:** Build scripts (TypeScript/Shell), bundling logic, test execution scripts, and npm packaging utilities.
* **Does NOT Own:** Core application logic (see `/src`), or the actual CI/CD workflow definitions (which reside in `.github/workflows/`).

## 🔑 Key Entry Files
* `build-bundle.ts` / `build.sh` - Scripts for compiling and bundling the CLI for production.
* `dev.ts` - Script for running the application in development mode with hot-reloading.
* `package-npm.ts` - Utility for preparing the npm package publication.
* `test-mcp.ts` / `test-commands.ts` - Custom test runners for specific subsystems.

## 🔄 Dependencies
* **Upstream (Depends on):** Source code in `/src`, dependencies in `package.json`, and the Bun runtime.
* **Downstream (Depended on by):** GitHub Actions workflows (in `.github/`), and developer local workflows.

## 📖 Read Next
* [Core Source Code](../src/README.md)
* [Production Bundle Prompt](../prompts/15-production-bundle.md)
