<p align="center">
  <img src="assets/icon.png" width="100" alt="VAULT Logo" />
</p>

<h1 align="center">VAULT</h1>

<p align="center">
  <b>A game launcher for Windows with controller support and local save management</b>
</p>

<p align="center">
  <a href="https://github.com/antnjhn/vault-launcher/releases/latest">
    <img src="https://img.shields.io/github/v/release/antnjhn/vault-launcher?style=flat-square&color=7c4dff" alt="Latest Release" />
  </a>
  <a href="LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue?style=flat-square" alt="License" />
  </a>
  <img src="https://img.shields.io/badge/platform-Windows-0078d4?style=flat-square" alt="Platform" />
  <img src="https://img.shields.io/badge/built_with-Tauri_2-ffc131?style=flat-square" alt="Built with Tauri" />
</p>

---

## Features

- **Controller Support** — Navigate the library using a gamepad (Xbox layout supported).
- **Per-Game Backgrounds** — Supports custom background images that crossfade during navigation.
- **Custom Cover Art** — Import logos and customize typography per game.
- **Playtime Tracking** — Records session count, total playtime, and last played date.
- **Save Management** — Automatic save location detection. Supports manual and automatic backups with one-click restore.
- **Uninstaller Integration** — Detects `unins000.exe` to offer uninstallation directly from the launcher.
- **State Detection** — Grays out games if the executable is no longer found on disk.
- **Xbox Mode** — Optional integration to launch games via Windows 11 Xbox Mode.
- **Frameless UI** — Fullscreen, minimal interface without window borders.

---

## Installation

### Pre-built Binaries

Visit the [Releases](https://github.com/antnjhn/vault-launcher/releases/latest) page to download the latest version:

- **`vault-launcher_x.x.x_x64-setup.exe`** (NSIS installer)
- **`vault-launcher_x.x.x_x64_en-US.msi`** (Windows Installer)

### Build from Source

**Prerequisites:**
- [Node.js](https://nodejs.org) (LTS)
- [Rust](https://www.rust-lang.org/tools/install)
- Windows 10/11

```bash
git clone https://github.com/antnjhn/vault-launcher.git
cd vault-launcher

npm install
npm run build
```

The compiled binaries will be output to `src-tauri/target/release/bundle/`.

---

## Controls

| Controller | Keyboard | Action |
|---|---|---|
| Left Stick Up/Down | Arrow Up/Down | Navigate game list |
| D-Pad Up/Down | Arrow Up/Down | Navigate game list |
| Right / D-Right | Arrow Right | Open game details |
| Left / D-Left | Arrow Left | Close details / Back |
| A | Enter | Open details / Launch game |
| B | Escape | Back / Close |
| X | — | Edit selected game |
| Y | — | Add new game |

---

## Usage

### Adding Games

1. Press **Y** on the controller or click **+** in the top-left.
2. Enter the game title.
3. Select the target `.exe` file.
4. (Optional) Provide a cover art image and background wallpaper.
5. Save the configuration.

### Save Management

Save files are detected automatically upon first launch. In the details panel:

- **BACKUP** — Creates a named snapshot of the current save state.
- **RESTORE** — Displays available backups (marked as `AUTO` or `MANUAL`) for restoration or deletion.

Automatic backups are generated upon game exit.

---

## Data Storage

Application data is stored locally at:
```
%APPDATA%\com.vault.launcher\
├── games.json          # Game library metadata
├── wallpapers/         # Background images
└── backups/            # Compressed save backups
```

---

## Technology Stack

- [Tauri 2](https://v2.tauri.app/)
- Rust (Backend process management and filesystem operations)
- Vanilla JS/CSS/HTML (Frontend)

---

## License

[MIT](LICENSE) © antnjhn
