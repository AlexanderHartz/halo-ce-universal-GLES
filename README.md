# Halo CE Universal - OpenGL ES 3.2 (Legacy Hardware Fork)

[![Original Project](https://img.shields.io/badge/Original_Project-cybersecurity/halo--ce--universal-blue)](https://github.com/cybersecurity/halo-ce-universal)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

This is a specialized fork of the [Halo: Combat Evolved decompilation port](https://github.com/cybersecurity/halo-ce-universal), specifically modified to route the renderer through **OpenGL ES 3.2** on Linux. 

This modification enables the game to run smoothly on older integrated GPUs (such as the Intel HD Graphics 4000 / Ivy Bridge) that lack full desktop OpenGL 4.5 Core support, but do support OpenGL ES 3 via Mesa drivers.

---

### ✅ Tested & Verified On
- **OS:** Linux Mint LMDE with XFCE
- **GPU:** Intel HD Graphics 4000 (Ivy Bridge)
- **Drivers:** Mesa

### 📦 Release Contents
- `halo` - Compiled executable for Linux (32-bit x86)
- `config.toml` - Default configuration file
- `assets/` - Game assets (fonts, HUD, titles)
- `README.txt` - Quick usage instructions

---

### 🚀 How to Use

1. **Download:** Download and extract the latest release ZIP.
2. **Game Data:** Obtain the original Halo: Combat Evolved Xbox game data. You can either:
   - Copy the `maps/` folder directly into the game directory.
   - Let the game extract it automatically on first run by providing an original `.xiso` or `.iso`.
3. **Run the Game:** 
   - **Standard:** Execute `./halo` in the terminal.
   - **⚠️ Important for Older GPUs:** If the game fails to start or experiences graphical issues, force Mesa to expose OpenGL ES 3.2 compatibility by running:
     ```bash
     export MESA_GLES_VERSION_OVERRIDE=3.2
     ./halo
     ```

### 📋 Requirements
- Linux OS with Mesa drivers.
- A GPU with OpenGL ES 3.2 support (or the ability to force it via Mesa environment overrides).
- Original Halo: Combat Evolved (Xbox) game files.

---

### 🎮 Multiplayer
*(Information retained from the original project)*

- **Multiplayer:** The game supports system link games on a local network and on the internet (up to 128 players). Linux, Windows, and Android machines can play in the same game using invite links. No central server is required.

---

### 🛠️ Build the Game

If you want to compile this fork yourself, you do not need the Xbox SDK. The port supplies the necessary SDK declarations.

1. Install Python and [ninja](https://ninja-build.org/).
2. Install Linux build dependencies (e.g., `libsdl3-dev`, `libgles2-mesa-dev`, `libegl1-mesa-dev`, `clang`).
3. In the root folder of the repository, run:
   ```bash
   python configure.py --release
   ninja linux
