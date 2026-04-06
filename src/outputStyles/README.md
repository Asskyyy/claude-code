# Output Styling (`/src/outputStyles`)

## 🎯 Purpose
This directory centralizes the definitions for how text is styled and formatted in the terminal (colors, typography, markdown rendering).

## 🏛️ Domain Boundaries
* **Owns:** Chalk/Ink color constants, markdown render themes.
* **Does NOT Own:** The UI components themselves.

## 🔑 Key Entry Files
* Style definitions.

## 🔄 Dependencies
* **Upstream (Depends on):** `chalk`, `ink`.
* **Downstream (Depended on by):** `/src/components`.

## 📖 Read Next
* [Components](../components/README.md)
