# Corne Wireless ZMK Firmware (5-Column Colemak)

This repository contains the ZMK configuration for my wireless **Corne (CRKBD) 5-column** split keyboard, running custom firmware built using [ZMK](https://zmk.dev/). The layout is based on **Colemak**, inspired by the principles of [Miryoku](https://github.com/manna-harbour/miryoku) — minimal finger travel, home-row mods, and layered functionality.

## Hardware

- **Keyboard**: Corne Wireless (5-column variant)
- **Firmware**: [ZMK Firmware](https://zmk.dev/)
- **Layout Style**: Colemak, Miryoku-inspired
- **Transport**: Bluetooth

---

## Features

- ✅ **Home row modifiers** (hold-tap) on Colemak base
- 🎛️ **Tap dance** for Bluetooth switching/clearing
- 🔢 **Numpad, Navigation, Function, and Media** layers
- 🧠 Thoughtful layer design for ergonomic workflows
- 🔐 All modifiers and layer access placed within thumb reach

---

## Layer Overview

### 🅱 Base Layer (Colemak)

- Miryoku-style home-row mods:
  - Left: `A`=Ctrl, `R`=Alt, `S`=Cmd, `T`=Shift
  - Right: `N`=Shift, `E`=Cmd, `I`=Alt, `O`=Ctrl
- Thumb keys: Tab, Backspace, Enter, Space, Apostrophe, Tilde
- Layout prioritizes minimal hand movement and reduced pinky use

### 🔢 Numpad Layer

- Access to numerals, math symbols, and punctuation
- Includes layered bracket/paren modifiers for coding

### 🧭 Navigation Layer

- Arrows and cursor movement keys
- Tap-dance-enabled Bluetooth switching (`BT1`, `BT2`, `CLR`)

### 🔧 Function Layer

- Traditional F-keys (F1–F12) mapped in a logical grid
- Primarily for dev/debug/IDE access

### 🎵 Media Layer

- Volume, mute, playback controls
- Bluetooth connection management

---

## Custom Behaviors

### 🏠 Home Row Modifiers (`&hm`)

```dts
flavor = "tap-preferred";
tapping-term-ms = 250;
```

- Modifier when held, character when tapped
- Enables efficient use of modifiers without finger travel

### 🔁 Tap Dance for Bluetooth (`&tdbt`)

```dts
bindings = <&bt BT_SEL 0>, <&bt BT_SEL 1>, <&bt BT_CLR>;
```

- Single tap: Switch to BT Profile 0
- Double tap: Switch to BT Profile 1
- Hold: Clear bonded devices

---

## Building and Flashing

> ⚠️ Be sure your environment is configured per [ZMK documentation](https://zmk.dev/docs/).

Build and flash for each half:

```bash
west build -b <left|right> -d build/<left|right> -- -DSHIELD=corne_<left|right>
west flash -d build/<left|right>
```

---

## Diagrams

> (Optional) Visual layer diagrams can be created using [`keymap-drawer`](https://github.com/caksoylar/keymap-drawer).

---

## License

MIT License – see `LICENSE`.  
Built on the excellent work of the ZMK and Miryoku communities.

---

## Author

Custom layout and configuration by [undergroundpost].
