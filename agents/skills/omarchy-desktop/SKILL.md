---
name: omarchy-desktop
description: Omarchy/Hyprland desktop contract for LET GUIs. Use when adding shortcuts, Wayland support, window rules, HiDPI, or any graphical tool; when Super-key bindings are proposed; or when the user runs /omarchy-desktop.
---

# Omarchy desktop contract

GUI tools in this organization must work as **native Wayland** apps on [Omarchy](https://omarchy.org/) (Hyprland). An X11-only or “disable the compositor Super key” path is a defect.

Full contract: issue labeled `platform:omarchy` in this repo. Do not copy that issue into this skill.

## Super is the compositor’s key

Default in-app chords use **Ctrl / Shift / Alt**. Do not bind Super (or Super+anything) unless the user rebinds it themselves.

Do not ship defaults that collide with Omarchy’s map. At minimum, leave these to the compositor:

- Super+Space (menus), Super+Return and Shift/Alt/Ctrl+Return (terminal / browser / tmux / Herdr)
- Super+W close, Super+F fullscreen, Super+T float, Super+O pop-out, Super+P pseudo, Super+J split
- Super+C / V / X clipboard, Super+Ctrl+V clipboard manager
- Super+K keybinding help, Super+1–0 and Super+Tab workspaces, Super+S scratchpad
- Super+Shift+Ctrl+A agent picker
- Print and Super+Print family (capture / color / OCR)
- Super+comma notifications, Super+Escape system menu, Super+Ctrl+L lock

Save/undo/fit-view in engineering apps: **Ctrl+S**, **Ctrl+Z**, and a fit-view chord that is **not** Super+F.

Every shortcut must be user-rebindable. Ship a printed map (`--help` or a `keymap` subcommand).

## Do

- Wayland-native; test on Omarchy
- In-app shortcuts only — never global/compositor grabs
- Follow session color-scheme and scale (HiDPI)
- Provide a **CLI for every action** an agent or script needs; GUI is not the only path
- Optional Hyprland window rules as a **snippet the user can paste**. Never write the user’s `~/.config/hypr/bindings.lua` for them

## Do not

- Overwrite Omarchy user config
- Require X11
- Bind Super by default
- Treat Wine as the supported Linux path
