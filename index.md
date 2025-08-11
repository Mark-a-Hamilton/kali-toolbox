# 🗂️ Kali-toolbox Index

Welcome to the **Kali-toolbox** index. This document provides a structured overview of all scripts, documentation, and assets included in the repository. Each entry is designed to support system maintenance, operational hygiene, and ethical transparency.

---

## 📜 Scripts

Scripts are located in the `scripts/` folder and are intended for installation to `/usr/local/bin` for global access.

| Script Name       | Description                                  | Documentation Link         |
|-------------------|----------------------------------------------|-----------------------------|
| `kali-update`     | Updates system packages and refreshes repos  | [`docs/kali-update.md`](docs/kali-update.md)  |
| `kali-cleanup`    | Removes orphaned packages and temp files     | [`docs/kali-cleanup.md`](docs/kali-cleanup.md) *(stub)* |
| `kali-diagnostics`| Runs basic system health checks              | [`docs/kali-diagnostics.md`](docs/kali-diagnostics.md) *(stub)* |

> 📌 *More scripts will be added as the toolbox evolves. Each should include internal usage documentation and logging behavior.*

---

## 📚 Documentation

Located in the `docs/` folder. Each script has a corresponding markdown file detailing:
- Purpose and scope
- Usage examples
- Dependencies
- Output format
- Logging and audit notes

---

## 🖼️ Assets

Visual aids are stored in the `assets/` folder and may include:
- Flowcharts of script logic
- Diagrams of operational workflows
- Screenshots for onboarding or usage

---

## 🔐 Audit & Traceability

The `.hashmap/` folder is reserved for:
- Hashes of script files (`.sha256`)
- Logged outputs for audit trails
- Timestamped execution records

This supports audit-grade traceability and ethical accountability.

---

## 🧭 Navigation

Return to the main project overview in [`README.md`](README.md).

For contribution guidelines and ethical framing, see [`docs/ethics.md`](docs/ethics.md) *(to be drafted)*.
