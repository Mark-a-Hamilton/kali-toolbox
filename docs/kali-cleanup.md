# 🧹 kali-cleanup

The `kali-cleanup` script is a modular hygiene wrapper for Kali Linux systems. It automates the removal of orphaned packages, clears cached files, and tidies up temporary directories. Designed for audit-grade traceability, it supports dry-run simulation and optional logging.

---

## 📦 Purpose

This script helps maintain a clean and efficient system by:
- Removing unused packages (`apt autoremove`)
- Clearing package cache (`apt clean`)
- Purging residual files from `/var/cache/apt/` and `/tmp/`
- Supporting dry-run and logging for safe, traceable execution

It is intended for post-update hygiene and does **not** perform any enumeration or security scanning.

---

## 🚀 Usage

### Basic cleanup

```bash
kali-cleanup
```

Performs all cleanup steps with no logging.

### Dry-run mode

```bash
kali-cleanup --dry-run
```

Simulates each step without making changes. Useful for previewing actions.

### With logging

```bash
kali-cleanup --log
```

Appends execution details to `/var/log/kali-cleanup.log`.

### Combined

```bash
kali-cleanup --dry-run --log
```

Simulates cleanup and logs the intended actions.

---

## ⚙️ Parameters

| Flag         | Description                                      |
|--------------|--------------------------------------------------|
| `--dry-run`  | Simulates cleanup steps without executing them   |
| `--log`      | Logs actions to `/var/log/kali-cleanup.log`      |
| `--help`     | Displays usage instructions                      |

---

## 📁 Output

Typical output includes:
- Confirmation of each step executed or simulated
- Summary of removed packages and cleared directories
- Optional log file with timestamped actions

Example log snippet:

```
=== kali-cleanup ===
2025-08-11 19:45:02
apt autoremove -y
apt clean
rm -rf /var/cache/apt/*
rm -rf /tmp/*
====================
```

---

## 🔐 Audit Notes

For traceability:
- Hash the script using `sha256sum`
- Log execution timestamps
- Store logs in `.hashmap/` if audit mode is active

Example:

```bash
sha256sum /usr/local/bin/kali-cleanup > .hashmap/kali-cleanup.hash
date > .hashmap/kali-cleanup.timestamp
```

---

## 📢 Disclaimer

This script performs system hygiene only. It does **not** modify user data, perform recon, or interact with network services.

Use responsibly and only on systems where you have explicit permission.
ike to add a `--verbose` flag, integrate `.hashmap` logging directly, or link this doc from your `index.md`.
