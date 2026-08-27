# Spec: Omarchy / Wayland desktop contract

Cross-cutting contract for any Linux Engineering Tools (LET) graphical user interface (GUI). Requirement [#1](https://github.com/linux-engineering-tools/community/issues/1). Skill (do not duplicate into skills): `agents/skills/omarchy-desktop/SKILL.md`. Terms: [`../../TERMS.md`](../../TERMS.md).

**Status:** draft. This is process + tests, not a tool repo. Upstream GUIs (FreeCAD, KiCad, ParaView) should meet it; LET-incubated GUIs **must**.

## Job

An engineer on a Linux Wayland desktop can tile, fullscreen, copy/paste, and use compositor or desktop chords while the tool is focused. In-app shortcuts live in a simple configuration file they can edit, so they can avoid conflicts with their operating system. Omarchy (Hyprland) is a test desktop and the example of that config style, not a key map other projects must copy.

## Inputs / outputs / standards

- Wayland (not X11-only as the supported path)
- xdg-desktop-portal for file pickers and capture where needed
- Session color-scheme and fractional scale
- In-app shortcut map as a user-editable text or JSON file, plus a printed map for agents

## CLI

Every GUI action an agent needs has a non-interactive CLI. Also:

```
<tool> keymap
<tool> keymap --json
```

`--json` matches [`keymap.schema.json`](keymap.schema.json) and names the config file. Default chords use Ctrl / Shift / Alt only. Every listed binding is rebindable.

## User keybinding file

Ship a small text or JSON file the user can edit without a settings GUI. Same idea as Omarchy's `~/.config/hypr/bindings.lua`: add, replace, or unbind a chord in one place. Document the path in `--help` and in `keymap` output.

The tool never writes the user's compositor or desktop config (`~/.config/hypr/` and equivalents).

## Defaults

Defaults use Ctrl / Shift / Alt so they do not steal Super, which most Linux shells already use. Save / undo / fit-view: Ctrl+S, Ctrl+Z, and a fit-view chord that is **not** Super+F.

If a default still collides with a user's desktop, they remap. Do not treat Omarchy's Super map as a reserved list other apps must match.

## Acceptance tests

- App starts on Wayland; Omarchy is a valid test stack; docs do not require X11.
- Documented user keybinding file; changing a chord there changes the running map (restart or reload is allowed).
- `keymap --json` lists every default binding as rebindable; default chords use Ctrl / Shift / Alt only (no Super).
- File picker via portal, not a raw X11 grab.
- Optional Hyprland window-rule snippet is **documentation**, never written to `~/.config/hypr/` by the tool.

XWayland-only is a defect if advertised as the Linux path. Wine is not the supported path.

## Upstream

File Wayland and shortcut-config defects on the GUI project (KiCad, FreeCAD, ParaView, PulseView). Ask for a user-editable keybinding file, not for that project to copy Omarchy's chords. LET does not fork them for key fights.

## License

N/A (contract). Incubated tools: Apache-2.0 unless matching an upstream license.
