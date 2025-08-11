# 🗂️ Kali-toolbox Index

Welcome to the **Kali-toolbox** index. This document provides a structured overview of all scripts, documentation, and assets included in the repository. The toolbox is designed for **system maintenance**, **operational hygiene**, and **ethically bounded diagnostics** on Kali Linux.

---

## 📜 Scripts

Scripts are located in the `scripts/` folder and are intended for installation to `/usr/local/bin` for global access.

| Script Name       | Description                                  | Documentation Link         |
|-------------------|----------------------------------------------|-----------------------------|
| `kali-update`     | Updates system packages and refreshes repos  | [`docs/kali-update.md`](docs/kali-update.md) |
| `kali-cleanup`    | Removes orphaned packages and temp files     | [`docs/kali-cleanup.md`](docs/kali-cleanup.md) |
| `kali-diagnostics`| Runs basic system health checks              | [`docs/kali-diagnostics.md`](docs/kali-diagnostics.md) |

📌 More scripts will be added as the toolbox evolves. Each includes internal usage documentation, optional logging (`--log`), and hashing (`--hashmap`) for traceability.

---

## 📚 Documentation

Located in the `docs/` folder. Each script has a corresponding markdown file detailing:

- Purpose and scope
- Usage examples
- Dependencies
- Output format
- Logging and audit notes

Additional documentation includes:
- [`docs/ethics.md`](docs/ethics.md): Ethical framing and responsible use
- `README.md`: Project overview and installation instructions

---

## 🖼️ Assets

Visual aids are stored in the `assets/` folder and may include:

- Flowcharts of script logic
- Diagrams of operational workflows
- Screenshots for onboarding or usage

---

## 🔐 Audit & Traceability

The `.hashmap/` folder supports audit-grade traceability:

- SHA256 hashes of script files
- Logged outputs for audit trails
- Timestamped execution records

This reinforces ethical accountability and supports client-facing reporting.

---

## 🧭 Navigation

- Return to the main project overview in [`README.md`](README.md)
- Review ethical principles in [`docs/ethics.md`](docs/ethics.md)
- Explore script documentation in the [`docs/`](docs/) folder
- View visual assets in the [`assets/`](assets/) folder
