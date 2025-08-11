# 🩺 kali-diagnostics

The `kali-diagnostics` script is a modular wrapper for basic system diagnostics in Kali Linux. It checks service status, network connectivity, and system health, with optional logging and hash-based traceability.

---

## 📦 Purpose

This script provides quick visibility into system status by:
- Checking key services
- Validating network connectivity
- Reporting uptime and resource usage
- Logging actions and hashing for audit-grade traceability

---

## 🚀 Usage

### Basic diagnostics

```bash
kali-diagnostics
```

Runs all checks with no logging or simulation.

### Dry-run mode

```bash
kali-diagnostics --dry-run
```

Simulates each check without executing.

### With logging

```bash
kali-diagnostics --log
```

Appends execution details to `/var/log/kali-diagnostics.log`.

### With hash-based audit

```bash
kali-diagnostics --hashmap
```

Generates a SHA-256 hash of the script and logs the timestamp to `.hashmap/`.

---

## ⚙️ Parameters

| Flag         | Description                                                  |
|--------------|--------------------------------------------------------------|
| `--dry-run`  | Simulates diagnostic steps without executing                 |
| `--log`      | Logs actions to `/var/log/kali-diagnostics.log`              |
| `--hashmap`  | Stores script hash and timestamp in `.hashmap/`              |
| `--help`     | Displays usage instructions                                  |

---

## 🔧 Checks Performed

| Command                 | Description                          |
|-------------------------|--------------------------------------|
| `systemctl status`      | Checks service status                |
| `ping -c 4 8.8.8.8`     | Validates external connectivity      |
| `uptime`                | Reports system uptime                |
| `free -h`               | Displays memory usage                |

---

## 📁 Output

Includes:
- Confirmation of each check executed or simulated
- Optional log file with timestamped actions
- Optional `.hashmap/` entries for audit traceability

---

## 📢 Disclaimer

This script wraps existing system commands and is intended solely for diagnostics. It does **not** perform any 
