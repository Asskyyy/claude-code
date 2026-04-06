# Scripts & Tooling (`/scripts`)

## Purpose
This directory contains utility scripts, build processes, and testing harnesses used to manage the development and compilation lifecycle of Claude Code.

## Owns
* Build scripts (TypeScript/Shell) and bundling logic.
* Test execution scripts tailored for specific subsystems.
* Scripts for running the application in local development mode.

## Does Not Own
* Core application logic (see `/src`).
* GitHub Actions CI/CD workflow definitions (which reside in `.github/workflows/`).

## Key Entry Files
* `build-bundle.ts` / `build.sh` - Scripts for compiling and bundling the CLI.
* `dev.ts` - Script for running the application in development mode.
* `test-mcp.ts` / `test-commands.ts` - Custom test runners for specific features.

## Read Next
* [Core Source Code](../src/README.md)