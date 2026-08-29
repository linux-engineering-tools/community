---
name: omarchy-desktop
description: Use when adding shortcuts, Wayland support, window rules, HiDPI, or any graphical tool; when a keybinding config or Super-key binding is proposed; or when the user runs /omarchy-desktop.
---

# Omarchy desktop contract

GUI tools in this organization must work as **native Wayland** apps. [Omarchy](https://omarchy.org/) (Hyprland) is a test desktop. An X11-only path is a defect. Telling the user to disable their compositor Super key is a defect. A closed, non-editable shortcut map is a defect.

Full contract: issue labeled `platform:omarchy` and [`specs/omarchy-desktop/`](../../../specs/omarchy-desktop/). Do not copy that spec into this skill. Existing FOSS display notes live in [`catalog/desktop.md`](../../../catalog/desktop.md). Those are literature, not a waiver of this contract for LET GUIs.

## Keybindings belong to the user

Ship a small user-editable config file (text or JSON). Omarchy's `~/.config/hypr/bindings.lua` is the example of that style, not a chord list other apps must copy.

Default in-app chords use **Ctrl / Shift / Alt**. Do not bind Super unless the user rebinds it themselves. If a default collides with their OS, they edit the file.

Every shortcut must be user-rebindable. Print the map (`keymap` or `keymap --json`) and the config path.

Save/undo/fit-view: **Ctrl+S**, **Ctrl+Z**, and a fit-view chord that is not Super+F.

## Do

- Wayland-native; test on Omarchy when you can
- In-app shortcuts only. Never global or compositor grabs
- Follow session color-scheme and scale (HiDPI)
- Provide a **CLI for every action** an agent or script needs; GUI is not the only path
- Optional Hyprland window rules as a **snippet the user can paste**. Never write the user's compositor config

## Do not

- Overwrite desktop or compositor user config
- Require X11
- Bind Super by default
- Treat Omarchy's Super map as the contract
- Treat Wine as the supported Linux path
