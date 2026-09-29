<div align="center">

<img src=".github/assets/logo.png" width="120" alt="Opticore logo" />

# Opticore Client

**A clean, client-side Fabric utility mod for Minecraft Java Edition 26.2**

[![Minecraft](https://img.shields.io/badge/Minecraft-26.2-38BDF8?style=for-the-badge&logo=minecraft&logoColor=white)](https://www.minecraft.net)
[![Fabric](https://img.shields.io/badge/Fabric-Loader%200.19%2B-A855F7?style=for-the-badge)](https://fabricmc.net)
[![License](https://img.shields.io/badge/License-CC0--1.0-22D3EE?style=for-the-badge)](LICENSE)
[![Build](https://img.shields.io/github/actions/workflow/status/YOUR_USERNAME/opticore-client/build.yml?style=for-the-badge&label=Build)](../../actions)

<img src=".github/assets/panorama_preview.png" width="640" alt="Opticore main menu preview" />

</div>

---

## ✨ Overview

Opticore Client is a **client-side-only** Fabric mod — it changes nothing about game logic or fairness, and adds nothing that gives an advantage over other players. It's branding, quality-of-life and a ClickGUI module framework: a custom main menu, a HUD watermark, and a set of small, honest client tweaks.

> **No unfair PvP modules.** Opticore intentionally ships no KillAura, reach, aimbot, or ESP-style modules. The Combat category exists as a home for fair, client-side aids only (e.g. indicators, timers) — see [Philosophy](#-philosophy).

## 🧩 Features

| | |
|---|---|
| 🪟 **Custom branding** | Window title, taskbar icon, and main-menu panorama, all swappable |
| 🎨 **6 menu themes** | Opticore, Ocean Deep, Aurora, Synth Sunset, Crimson Night, Graphite, Frost — switch in Resource Packs |
| 🖱️ **ClickGUI** | Press **Right Shift** — 6 tabbed categories, drag-to-move panels, alphabetically sorted modules |
| ⌨️ **Per-module keybinds** | Right-click any module to bind a key |
| 📝 **Live description panel** | Hover a module or setting to read what it does |
| 🔔 **Toggle notifications** | Bottom-right pop-up whenever a module is switched on/off |
| 🧱 **Small, typed module API** | Add a module in one file + one line — booleans, sliders and mode-cycles included |

## 📂 Module list

| Category | Module | What it does |
|---|---|---|
| Render | `Fullbright` | Pushes gamma past the vanilla slider limit |
| Render | `FOV` | Field of view beyond the vanilla 30–110 range |
| Player | `Freecam` | Detaches the camera from your player |
| Client | `Notifications` | Toggle pop-ups, shown bottom-right |
| Client | `Font` | ClickGUI text size, weight and shadow |
| Client | `HUD` | Placeholder — reserved for future HUD elements |
| Client | `UI` | ClickGUI accent theme and panel opacity |
| Combat / Movement / Misc | — | Empty on purpose — see [Contributing](#-contributing) |

## 📥 Installation

1. Install [Fabric Loader](https://fabricmc.net/use/) for **Minecraft 26.2**.
2. Download the latest `opticore-*.jar` from [Releases](../../releases).
3. Get [Fabric API](https://modrinth.com/mod/fabric-api) and [Fabric Language Kotlin](https://modrinth.com/mod/fabric-language-kotlin) for 26.2.
4. Drop all three jars into your `.minecraft/mods` folder.

## 🛠️ Building from source

Requires **JDK 25**.

```bash
git clone https://github.com/YOUR_USERNAME/opticore-client.git
cd opticore-client
./gradlew build        # Linux / macOS
gradlew.bat build       # Windows
```

The built jar is at `build/libs/opticore-<version>.jar`. Run `./gradlew runClient` (or `gradlew.bat runClient`) to test in a dev environment.

## 🎨 Menu themes

Switch in **Options → Resource Packs**: move an "Opticore Theme: ..." pack to the enabled side and put it above the others. Regenerate or add themes with `tools/generate_assets.py` (needs `pip install numpy pillow`).

## ⚖️ Philosophy

Opticore stays on the fair side of "utility mod":

- ✅ Client-side rendering and UI (fullbright, FOV, freecam, HUD, themes)
- ❌ Anything that reads or acts on data the vanilla client wouldn't normally have, or that automates combat/movement in a way another player couldn't match manually

If you fork this project, please keep that line where it is — it's the whole point of the name.

## 🤝 Contributing

Adding a module is one class + one line:

```kotlin
// 1. extend Module, put it in module/impl/
class MyModule : Module("MyModule", "What it does.", Category.MISC) { ... }

// 2. register it
ModuleManager.register(..., MyModule())
```

PRs welcome for new **fair** modules, bug fixes, and new menu themes.

## 📜 License

Released under [CC0-1.0](LICENSE) — public domain, no attribution required. Minecraft is a trademark of Mojang Synergies AB; this project is not affiliated with or endorsed by Mojang or Microsoft.

---

<div align="center">
<sub>Built with 🩵 using Fabric, Fabric Language Kotlin, and way too much time spent on gradients.</sub>
</div>
