# wasoom

> A modern, browser-based WebAssembly port of classic DOOM with OPL3 FM music synthesis, sound effects, mouse look, persistent saves, and custom WAD support.

---

> [!IMPORTANT]
> **Project Status (Pre-1.0)**
> **wasoom** is currently pre-release and distributed as a **closed-source build**. This repository provides the ready-to-run compiled binaries and web assets. The complete source code, build harnesses, and tooling will be opened up once the project reaches **version 1.0**.

---

## ✨ Features

- **WebAssembly Engine**: High-performance DOOM engine running client-side directly in modern web browsers via WebAssembly.
- **OPL3 FM Music & Sound**: Genuine Sound Blaster / AdLib OPL3 emulation synthesized in real time via the Web Audio API alongside digitized sound effects.
- **Persistent Saves**: Save games and configurations are automatically persisted to your browser via IndexedDB (IDBFS), isolated per game.
- **WAD Manager & Drag-and-Drop**:
  - Play bundled games out of the box.
  - Drag and drop your own **IWADs** (e.g., *DOOM II*, *The Ultimate DOOM*, *Final DOOM*) or **PWADs** (mods, total conversions, custom map packs) directly into the browser.
- **Modern Controls**:
  - Optional **WASD** movement (with intelligent fallback so typing save game names still works).
  - Mouse look with pointer lock (left-click fire, right-click interact/use, mouse wheel weapon cycling).
  - **Always Run** toggle.
- **Cheats Menu**: Built-in in-game cheat overlay (press `` ` ``) with quick buttons for God Mode (`IDDQD`), All Weapons & Keys (`IDKFA`), No-Clip (`IDCLIP`), level warp (`IDCLEV`), and more.
- **True Fullscreen**: Seamless aspect-ratio preserving fullscreen mode (<kbd>Alt</kbd> + <kbd>Enter</kbd>).

---

## 🎮 Included Games

**wasoom** includes the following free and shareware games ready to launch from the main menu:

| Game | Description |
| :--- | :--- |
| **DOOM (Shareware)** | Episode 1: *Knee-Deep in the Dead* (`doom1.wad`) |
| **Freedoom: Phase 1** | Free software replacement for *The Ultimate DOOM* (4 episodes) |
| **Freedoom: Phase 2** | Free software replacement for *DOOM II* (32 levels) |

*Own the original games? Simply drag and drop your retail `DOOM.WAD` or `DOOM2.WAD` onto the page to play!*

---

## 🚀 Quick Start

Because modern browsers restrict WebAssembly, Web Audio, and fetch requests over the `file:///` protocol, the files must be served over an HTTP server.

### Option 1: Using Python
If you have Python installed:
```bash
# Navigate to the dist folder (or project root if serving dist)
cd dist
python -m http.server 8000
```
Then navigate to `http://localhost:8000` in your browser.

### Option 2: Using Node.js (npx)
```bash
cd dist
npx serve .
```

### Option 3: GitHub Pages
You can deploy the contents of the `build` directory straight to **GitHub Pages**:
1. Push the repository to GitHub.
2. In your repository settings, go to **Pages**.
3. Choose the branch and folder (e.g. `main` / `build` or root depending on your repository structure) and deploy.

---

## ⌨️ Controls & Keybindings

| Action | Controls |
| :--- | :--- |
| **Move** | <kbd>W</kbd> <kbd>A</kbd> <kbd>S</kbd> <kbd>D</kbd> or Arrow Keys |
| **Fire** | Left Mouse Button or <kbd>Ctrl</kbd> |
| **Use / Open Doors** | Right Mouse Button or <kbd>Space</kbd> |
| **Strafe** | <kbd>A</kbd> / <kbd>D</kbd> (with WASD on) or <kbd>Alt</kbd> + Left/Right Arrow |
| **Run** | Hold <kbd>Shift</kbd> (or toggle **Always run**) |
| **Change Weapon** | Mouse Scroll Wheel or Number keys <kbd>1</kbd>–<kbd>7</kbd> |
| **Automap** | <kbd>Tab</kbd> |
| **Pause** | <kbd>Pause</kbd> |
| **Game Menu** | <kbd>Esc</kbd> / <kbd>Enter</kbd> |
| **Cheats Overlay** | <kbd>`</kbd> (Backquote / Tilde) |
| **Fullscreen** | <kbd>Alt</kbd> + <kbd>Enter</kbd> |
| **Mouse Capture** | Click canvas to lock mouse; press <kbd>Esc</kbd> to release |

---

## 📦 Loading Custom WADs

You can load your own DOOM-compatible WAD files directly in the browser:

1. Open **wasoom** in your browser.
2. Under the game selection menu, click **+ Add WAD files** or drag and drop `.wad` files anywhere onto the window.
3. **IWADs** (full standalone games) will appear under the *Games* list with their own play button and independent save slots.
4. **PWADs** (level packs, texture packs, sound mods) will automatically attach as active add-ons to whichever game you launch.

---

## 🗺️ Roadmap to 1.0

- [x] WebAssembly port with hardware canvas scaling
- [x] OPL3 FM sound synthesis + digital SFX
- [x] IndexedDB persistent save storage
- [x] PWAD & IWAD drag-and-drop loading
- [x] Mouse look & customizable controls
- [ ] Mobile & touch control overlay
- [ ] Gamepad / Game Controller API support
- [ ] Custom keybinding remapping menu
- [ ] Multiplayer / WebRTC networking experimentation
- [ ] **v1.0 Milestone**: Public source code release and build documentation

---

## ⚖️ Legal & Acknowledgments

- **DOOM** is a registered trademark of id Software LLC, a ZeniMax Media company.
- *DOOM Shareware Episode 1* is distributed in accordance with id Software's original shareware distribution guidelines.
- **Freedoom** is released under its modified BSD license (see `FREEDOOM-COPYING.txt` and `FREEDOOM-CREDITS.txt`).
- Powered by [`doomgeneric`](https://github.com/ozkl/doomgeneric) and compiled with [Emscripten](https://emscripten.org/).
