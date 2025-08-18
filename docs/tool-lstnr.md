# tool-lstnr

## 🧰 Purpose
Start a listener on a specified port using `socat` (preferred) or `netcat` (fallback). Includes dry-run mode, logging, and hash-based traceability. Designed for authorized, defensive use only.

## 🧑‍💻 Author
Mark Hamilton │ Co-Pilot AI assisted

## 📦 Package
toolbox

## 🛡️ Ethical Scope
This tool is passive and non-exploitative. It does not initiate outbound connections or payloads. Intended for authorized environments only. See `ethics_AI.md` for usage boundaries.

## ⚙️ Usage
```bash
tool-lstnr [--port <PORT>] [--dry-run] [--log] [--hashmap]
```

## 🧪 Examples
```bash
tool-lstnr
tool-lstnr --port 5555 --log --hashmap
```

## 🧩 Flags
| Flag        | Description                                      |
|-------------|--------------------------------------------------|
| `--port`    | Specify listener port (default: 4444)            |
| `--dry-run` | Simulate setup without launching listener        |
| `--log`     | Log session output to `~/Documents/listener.log` |
| `--hashmap` | Generate `.hashmap` files for audit traceability |

## 📂 Output Files
- `~/Documents/listener.log`: Session log (if `--log` used)
- `~/Documents/.hashmap/tool-lstnr.hash`: SHA256 hash of script
- `~/Documents/.hashmap/tool-lstnr.timestamp`: Launch timestamp

## 🔗 Related Tools
- `tool-box`: Index and help parser
- `tool-diag`: Diagnostic wrapper
- `tool-update`: Toolbox updater

## 🧠 Contributor Notes
This tool replaces legacy `nc` and `socat` scripts. It is modular, traceable, and aligned with toolbox standards. Metadata block is compatible with `tool-box` indexing.
