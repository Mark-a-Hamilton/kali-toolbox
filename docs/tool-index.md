# 🧭 tool-index

`tool-index` is the central listing and help utility for the Kali Toolbox. It parses embedded metadata from each tool script and displays purpose, version, and usage instructions in a clean, modular format.

---

## 📦 Purpose

This tool provides:

- A searchable index of all `tool-*` scripts
- Metadata parsing for purpose and version
- Help block extraction for individual tools
- Clean formatting and alignment for readability

---

## 🚀 Usage

### List All Tools
```bash
tool-index
```
Displays all available tools with purpose and version.

### View Help for Specific Tool
```bash
tool-index tool-diag
```
Displays the embedded help block for `tool-diag`.

---

## ⚙️ Parameters

| Argument        | Description                                      |
|------------------|--------------------------------------------------|
| `<tool-name>`    | Displays help block for the specified tool       |
| (none)           | Lists all tools with metadata summary            |

---

## 🔧 Features

- Parses `Script Purpose` and `Version` from comment blocks
- Trims and formats output for clean alignment
- Ignores code lines to avoid parsing errors
- Supports future expansion via `format_metadata()` function

---

## 📁 Output

- Console listing of all tools with metadata
- Help block display for individual tools
- Fallback messaging for missing or malformed metadata

---

## 🤖 AI Usage Disclosure

This tool was co-authored with AI assistance. For details on ethical AI integration and authorship standards, see the [AI.md](https://github.com/Mark-a-Hamilton/Mark-a-Hamilton.github.io/blob/main/ethics_AI.md) file in the root directory.
