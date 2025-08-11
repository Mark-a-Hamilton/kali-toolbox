# 🩺 kali-diagnostics

The `kali-diagnostics` script provides a modular wrapper for system health checks. It runs a series of diagnostic commands to assess uptime, resource usage, service status, and kernel messages. Designed for audit-grade traceability, it supports dry-run simulation and optional logging.

---

## 📦 Purpose

This script helps users:
- Monitor system health and performance
- Identify failed services or resource bottlenecks
- Capture diagnostic output for audit or support
- Run checks safely with dry-run preview

It is intended for passive diagnostics only and does **not** perform any enumeration or active scanning.

---

## 🚀 Usage

### Basic diagnostics

```bash
kali-diagnostics
```

Runs all checks and prints output to terminal.

### Dry-run mode

```bash
kali-diagnostics --dry-run
```

Simulates each check without executing commands.

### With logging

```bash
kali-diagnostics --log
```

Appends full output to `/var/log/kali-diagnostics.log`.

### Combined

```bash
kali-diagnostics --dry-run --log
```

Simulates checks and logs the intended actions.

---

## ⚙️ Parameters

| Flag         | Description                                      |
|--------------|--------------------------------------------------|
| `--dry-run`  | Simulates diagnostic steps without executing     |
| `--log`      | Logs output to `/var/log/kali-diagnostics.log`   |
| `--help`     | Displays usage instructions                      |

---

## 🔍 Checks Performed

| Check Command              | Description                          |
|---------------------------|--------------------------------------|
| `uptime`                  | System uptime and load averages      |
| `df -h`                   | Disk usage in human-readable format  |
| `free -m`                 | Memory usage in megabytes            |
| `top -b -n 1 | head -20`  | Snapshot of top processes            |
| `systemctl --failed`      | List of failed services              |
| `dmesg | tail -20`        | Recent kernel messages               |

---

## 📁 Output

Output includes:
- Timestamped execution summary
- Results of each diagnostic check
- Optional log file with full output

Example log snippet:

```
=== kali-diagnostics ===
2025-08-11 20:02:17
▶ uptime
  20:02:17 up 3 days,  4:12,  2 users,  load average: 0.15, 0.10, 0.05
▶ df -h
  Filesystem      Size  Used Avail Use% Mounted on
  /dev/sda1        50G   20G   28G  42% /
...
========================
```

---

## 🔐 Audit Notes

For traceability:
- Hash the script using `sha256sum`
- Log execution timestamps
- Store logs in `.hashmap/` if audit mode is active

Example:

```bash
sha256sum /usr/local/bin/kali-diagnostics > .hashmap/kali-diagnostics.hash
date > .hashmap/kali-diagnostics.timestamp
```

---

## 📢 Disclaimer

This script performs passive system diagnostics only. It does **not** modify system state, perform recon, or interact with external services.

Use responsibly and only on systems where you have explicit permission.
