# 🔄 tool-update

`tool-update` is a modular update utility for Kali Linux. It wraps system update commands with optional dry-run, logging, and hash-based audit support, ensuring safe and traceable package management.

---

## 📦 Purpose

This tool simplifies and secures system updates by:

- Running `apt update` and `apt upgrade` with confirmation
- Supporting dry-run simulation for safe previewing
- Logging update actions with timestamps
- Generating SHA-256 hashes for audit traceability

---

## 🚀 Usage

### Basic Update
```bash
tool-update
```
Performs a full system update.

### Dry-Run Mode
```bash
tool-update --dry-run
```
Simulates update steps without executing.

### With Logging
```bash
tool-update --log
```
Appends update actions to `/var/log/tool-update.log`.

### With Hash-Based Audit
```bash
tool-update --hashmap
```
Generates a SHA-256 hash of the script and logs the timestamp to `.hashmap/`.

---

## ⚙️ Parameters

| Flag         | Description                                      |
|--------------|--------------------------------------------------|
| `--dry-run`  | Simulates update steps without executing         |
| `--log`      | Logs actions to `/var/log/tool-update.log`       |
| `--hashmap`  | Stores script hash and timestamp in `.hashmap/`  |
| `--help`     | Displays usage instructions                      |

---

## 🔧 Steps Performed

| Command             | Description                        |
|---------------------|------------------------------------|
| `apt update`        | Refreshes package lists            |
| `apt upgrade -y`    | Installs available updates         |

---

## 📁 Output

- Console summary of update actions
- Optional log file with timestamped entries
- Optional `.hashmap/` entry for audit traceability

---

## 🤖 AI & Ethics Usage Disclosure

This tool was co-authored with AI assistance. For full details on ethical integration, traceability, and responsible authorship, see [ethics_AI.md](https://github.com/Mark-a-Hamilton/Mark-a-Hamilton.github.io/blob/main/ethics_AI.md).

