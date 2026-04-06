# Native TypeScript (`/src/native-ts`)

## 🎯 Purpose
This directory houses components that rely on native platform bindings or low-level Node features, abstracted behind a TypeScript interface.

## 🏛️ Domain Boundaries
* **Owns:** Platform-specific bindings and native integrations.
* **Does NOT Own:** General pure utilities (see `/src/utils`).

## 🔑 Key Entry Files
* Native wrappers.

## 🔄 Dependencies
* **Upstream (Depends on):** Node-gyp, native addons.
* **Downstream (Depended on by):** Specific CLI features requiring native OS hooks.

## 📖 Read Next
* [Core Source Code](../README.md)
