<p align="center">
  <img src="assets/icon.png" width="100" alt="VAULT Logo" />
</p>

<h1 align="center">VAULT</h1>

<p align="center">
  <b>A fast, aesthetic game launcher with controller support, save management, and Xbox Mode</b>
</p>

<p align="center">
  <a href="https://github.com/anthn/vault-launcher/releases/latest">
    <img src="https://img.shields.io/github/v/release/anthn/vault-launcher?style=flat-square&color=7c4dff" alt="Latest Release" />
  </a>
  <a href="LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue?style=flat-square" alt="License" />
  </a>
  <img src="https://img.shields.io/badge/platform-Windows-0078d4?style=flat-square" alt="Platform" />
  <img src="https://img.shields.io/badge/built_with-Tauri_2-ffc131?style=flat-square" alt="Built with Tauri" />
</p>

---

## ✨ Features

- 🎮 **Full Controller Support** — Navigate your entire library with a gamepad (Xbox recommended)
- 🖼️ **Per-Game Wallpapers** — Set custom backgrounds that crossfade as you browse
- 🎨 **Custom Cover Art** — Import logos and set custom fonts/colors per game
- ⏱️ **Playtime Tracking** — Automatic session counting, total playtime, and last played date
- 💾 **Save Backup & Restore** — Automatic save detection with manual/auto backup, custom naming, and one-click restore
- 🗑️ **Smart Uninstaller** — Detects `unins000.exe` and offers run uninstaller / delete folder / remove from launcher
- 🔍 **Installation Detection** — Automatically detects if a game is uninstalled and grays it out
- 🕹️ **Xbox Mode** — Launch games in Windows 11 Xbox Mode with one click
- 🖥️ **Fullscreen & Frameless** — Immersive, distraction-free UI

---

## 📥 Installation

### Download (Recommended)

Go to the [**Releases**](https://github.com/anthn/vault-launcher/releases/latest) page and download:

- **`vault-launcher_x.x.x_x64-setup.exe`** — NSIS installer (recommended)
- **`vault-launcher_x.x.x_x64_en-US.msi`** — Windows Installer package

### Build from Source

**Prerequisites:**
- [Node.js](https://nodejs.org) (LTS)
- [Rust](https://www.rust-lang.org/tools/install)
- Windows 10/11

```bash
# Clone the repo
git clone https://github.com/anthn/vault-launcher.git
cd vault-launcher

# Install dependencies
npm install

# Run in development mode
npm start

# Build production release
npm run build
```

The built executables will be in `src-tauri/target/release/bundle/`.

---

## 🎮 Controls

| Controller | Keyboard | Action |
|---|---|---|
| Left Stick ↑↓ | Arrow Up/Down | Navigate game list |
| D-Pad ↑↓ | Arrow Up/Down | Navigate game list |
| Right → / D-Right | Arrow Right | Open game details |
| Left ← / D-Left | Arrow Left | Close details / Back |
| A | Enter | Open details / Launch game |
| B | Escape | Back / Close |
| X | — | Edit selected game |
| Y | — | Add new game |

---

## 🕹️ Adding Games

1. Press **Y** on controller or click **+** in the top-left
2. Enter the game name
3. Browse to the `.exe` file
4. Optionally pick a cover art image (logo)
5. Optionally pick a background wallpaper
6. Hit **Save Game**

---

## 💾 Save Management

VAULT automatically detects save files when you launch a game for the first time. From the game details panel:

- **BACKUP** — Create a named manual backup of your saves
- **RESTORE** — Browse all backups (tagged as `AUTO` or `MANUAL`), restore or delete them

Automatic backups are created every time you close a game.

---

## 📂 Data Storage

All data is stored in:
```
%APPDATA%\com.vault.launcher\
├── games.json          # Game library
├── wallpapers/         # Copied wallpaper images
└── backups/            # Save file backups (per game)
```

---

## 🛠️ Tech Stack

- **[Tauri 2](https://v2.tauri.app/)** — Lightweight native app framework
- **Rust** — Backend (save detection, backup/restore, process management)
- **Vanilla JS/CSS/HTML** — Frontend (no framework overhead)

---

## 📄 License

[MIT](LICENSE) © anthn
