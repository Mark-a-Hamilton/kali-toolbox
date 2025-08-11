# 🔄 kali-update

The `kali-update` script is a modular wrapper for updating a Kali Linux system. It consolidates standard package management commands into a single, auditable workflow, with support for dry-run simulation, logging, and hash-based traceability.

---

## 📦 Purpose

This script simplifies routine update tasks by:
- Refreshing package lists
- Upgrading installed packages
- Removing unused packages and clearing cache
- Logging actions and hashing for audit-grade traceability

It is intended for system maintenance only and does **not** introduce any new security functionality.

---

## 🚀 Usage

### Basic update

```bash
kali-update
```

Runs all update steps with no logging or simulation.

### Dry-run mode

```bash
kali-update --dry-run
```

Simulates each step without making changes.

### With logging

```bash
kali-update --log
```

Appends execution details to `/var/log/kali-update.log`.

### With hash-based audit

```bash
kali-update --hashmap
```

Generates a SHA-256 hash of the script and logs the timestamp to `.hashmap/`.

### Combined

```bash
kali-update --log --hashmap
```

Performs update, logs actions, and stores audit artifacts.

---

## ⚙️ Parameters

| Flag         | Description                                                  |
|--------------|--------------------------------------------------------------|
| `--dry-run`  | Simulates update steps without executing                     |
| `--log`      | Logs actions to `/var/log/kali-update.log`                   |
| `--hashmap`  | Stores script hash and timestamp in `.hashmap/`              |
| `--help`     | Displays usage instructions                                  |

---

## 🔧 Steps Performed

| Command              | Description                          |
|----------------------|--------------------------------------|
| `apt update`         | Refreshes package lists              |
| `apt upgrade -y`     | Upgrades installed packages          |
| `apt autoremove -y`  | Removes orphaned packages            |
| `apt clean`          | Clears package cache                 |

---

## 📁 Output

Output includes:
- Confirmation of each step executed or simulated
- Optional log file with timestamped actions
- Optional `.hashmap/` entries for audit traceability

Example log snippet:

```
=== kali-update ===
2025-08-11 20:15:42
apt update
apt upgrade -y
apt autoremove -y
apt clean
===================
```

Example audit entries:

```bash
.sha256sum /usr/local/bin/kali-update > .hashmap/kali-update.hash
date > .hashmap/kali-update.timestamp
```

---

## 📢 Disclaimer

This script wraps existing system commands and is intended solely for system maintenance. It does **not** perform any security scanning, enumeration, or offensive actions.

Use responsibly and only in environments where you have explicit permission.
