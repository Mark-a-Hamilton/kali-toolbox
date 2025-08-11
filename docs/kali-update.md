# 🔄 kali-update

The `kali-update` script is a utility wrapper designed to streamline the process of updating a Kali Linux system. It consolidates standard package management commands into a single, auditable workflow, with optional logging and dry-run support.

---

## 📦 Purpose

This script simplifies routine update tasks by:
- Refreshing package lists
- Upgrading installed packages
- Cleaning up residual files
- Logging execution for traceability

It is intended for system maintenance only and does **not** introduce any new security functionality.

---

## 🚀 Usage

### Basic execution

```bash
kali-update
```

This will:
1. Run `apt update` to refresh package lists
2. Run `apt upgrade -y` to upgrade all packages
3. Optionally run `apt autoremove` and `apt clean` to tidy up

### With logging

```bash
kali-update | tee /var/log/kali-update.log
```

This captures output for audit purposes.

### Dry-run mode *(if implemented)*

```bash
kali-update --dry-run
```

Simulates the update process without making changes.

---

## ⚙️ Dependencies

- `apt`
- `dpkg`
- Bash shell (`#!/bin/bash`)

Ensure the script is executable and installed to `/usr/local/bin`:

```bash
sudo cp scripts/kali-update /usr/local/bin/
sudo chmod +x /usr/local/bin/kali-update
```

---

## 📁 Output

Typical output includes:
- Number of packages to upgrade
- Summary of changes
- Cleanup actions performed

If logging is enabled, output is saved to `/var/log/kali-update.log` or a user-defined path.

---

## 🔐 Audit Notes

For traceability:
- Hash the script using `sha256sum`
- Log execution timestamps
- Store logs in `.hashmap/` if audit mode is active

Example:

```bash
sha256sum /usr/local/bin/kali-update > .hashmap/kali-update.hash
date > .hashmap/kali-update.timestamp
```

---

## 📢 Disclaimer

This script wraps existing system commands and is intended solely for system maintenance. It does **not** perform any security scanning, enumeration, or offensive actions.

Use responsibly and only in environments where you have explicit permission.
