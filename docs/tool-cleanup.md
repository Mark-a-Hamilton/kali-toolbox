# 🧹 tool-cleanup

`tool-cleanup` is a modular system hygiene tool for Kali Linux. It performs safe cleanup operations—removing orphaned packages, clearing cache, and reporting disk usage—with optional dry-run, logging, and hash-based audit support.

---

## 📦 Purpose

This tool helps maintain operational hygiene by:

- Removing unused packages
- Clearing package cache
- Reporting disk usage
- Logging actions with timestamps
- Generating SHA-256 hashes for audit traceability

---

## 🚀 Usage

### Basic Cleanup
```bash
tool-cleanup
```
Runs all cleanup steps directly.

### Dry-Run Mode
```bash
tool-cleanup --dry-run
```
Simulates each step without making changes.

### With Logging
```bash
tool-cleanup --log
```
Appends execution details to `/var/log/tool-cleanup.log`.

### With Hash-Based Audit
```bash
tool-cleanup --hashmap
```
Generates a SHA-256 hash of the script and logs the timestamp to `.hashmap/`.

---

## ⚙️ Parameters

| Flag         | Description                                      |
|--------------|--------------------------------------------------|
| `--dry-run`  | Simulates cleanup steps without executing        |
| `--log`      | Logs actions to `/var/log/tool-cleanup.log`      |
| `--hashmap`  | Stores script hash and timestamp in `.hashmap/`  |
| `--help`     | Displays usage instructions                      |

---

## 🔧 Steps Performed

| Command             | Description                        |
|---------------------|------------------------------------|
| `apt autoremove -y` | Removes orphaned packages          |
| `apt clean`         | Clears package cache               |
| `df -h`             | Displays disk usage summary        |

---

## 📁 Output

- Confirmation of each step (executed or simulated)
- Optional log file with timestamped actions
- Optional `.hashmap/` entry for audit traceability

---

## 📢 Disclaimer

This script wraps standard system commands for hygiene purposes only. It does **not** perform scanning, enumeration, or offensive actions. Use responsibly and only in environments where you have explicit permission.

---

## 🤖 AI & Ethics Disclosure  

This tool was co-authored with AI assistance. For full details on ethical integration, traceability, and responsible authorship, see [ethics_AI.md]([https://mark-a-hamilton.github.io/main/ethics_AI.md](https://github.com/Mark-a-Hamilton/Mark-a-Hamilton.github.io/blob/main/ethics_AI.md)).  
🔙 [Return to Kali-toolbox](https://github.com/Mark-a-Hamilton/kali-toolbox)
