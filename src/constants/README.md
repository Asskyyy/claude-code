# Constants (`/src/constants`)

## 🎯 Purpose
This directory stores global, hardcoded values used consistently across the application to prevent magic numbers and strings.

## 🏛️ Domain Boundaries
* **Owns:** Global enums, default configuration limits, URL endpoints, and environment variable keys.
* **Does NOT Own:** Dynamic state or complex utility functions.

## 🔑 Key Entry Files
* Shared constant exports.

## 🔄 Dependencies
* **Upstream (Depends on):** None.
* **Downstream (Depended on by):** The entire application.

## 📖 Read Next
* [Types](../types/README.md)
