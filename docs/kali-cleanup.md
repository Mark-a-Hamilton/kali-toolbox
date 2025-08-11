# 🧹 kali-cleanup

The `kali-cleanup` script is a modular wrapper for system hygiene tasks in Kali Linux. It removes orphaned packages, clears cache, and validates disk usage—all with optional logging and hash-based traceability.

---

## 📦 Purpose

This script helps maintain a clean and efficient system by:
- Removing unused packages
- Clearing package cache
- Reporting disk usage
- Logging actions and hashing for audit-grade traceability

---

## 🚀 Usage

### Basic cleanup

```bash
kali-cleanup
```

Runs all cleanup steps with no logging or simulation.

### Dry-run mode

```bash
kali-cleanup --dry-run
```

Simulates each step without making changes.

### With logging

```bash
kali-cleanup --log
```

Appends execution details to `/var/log/kali-cleanup.log`.

### With hash-based audit

```bash
kali-cleanup --hashmap
```

Generates a SHA-256 hash of the script and logs the timestamp to `.hashmap/`.

---

## ⚙️ Parameters

| Flag         | Description                                                  |
|--------------|--------------------------------------------------------------|
| `--dry-run`  | Simulates cleanup steps without executing                    |
| `--log`      | Logs actions to `/var/log/kali-cleanup.log`                  |
| `--hashmap`  | Stores script hash and timestamp in `.hashmap/`              |
| `--help`     | Displays usage instructions                                  |

---

## 🔧 Steps Performed

| Command               | Description                          |
|-----------------------|--------------------------------------|
| `apt autoremove -y`   | Removes orphaned packages            |
| `apt clean`           | Clears package cache                 |
| `df -h`               | Displays disk usage summary          |

---

## 📁 Output

Includes:
- Confirmation of each step executed or simulated
- Optional log file with timestamped actions
- Optional `.hashmap/` entries for audit traceability

---

## 📢 Disclaimer

This script wraps existing system commands and is intended solely for system hygiene. It does **not** perform any security scanning or enumeration. Use responsibly and only in environments where you have explicit permission.
enumeration, scanning, or offensive actions. Use responsibly and only in environments where you have explicit permission.
