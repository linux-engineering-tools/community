# Spec: Omarchy / Wayland desktop contract

Cross-cutting contract for any Linux Engineering Tools (LET) graphical user interface (GUI). Requirement [#1](https://github.com/linux-engineering-tools/community/issues/1). Skill (do not duplicate into skills): `agents/skills/omarchy-desktop/SKILL.md`. Terms: [`../../TERMS.md`](../../TERMS.md).

**Status:** draft. This is process + tests, not a tool repo. Upstream GUIs (FreeCAD, KiCad, ParaView) should meet it; LET-incubated GUIs **must**.

## Job

An engineer on Omarchy (Hyprland / Wayland) can tile, fullscreen, copy/paste, and open the compositor menu while the tool is focused. Super-key chords stay with the compositor.

## Inputs / outputs / standards

- Wayland (not X11-only as the supported path)
- xdg-desktop-portal for file pickers and capture where needed
- Session color-scheme and fractional scale
- In-app shortcut map as text or JSON for agents

## CLI

Every GUI action an agent needs has a non-interactive CLI. Also:

```
<tool> keymap
<tool> keymap --json
```

`--json` matches [`keymap.schema.json`](keymap.schema.json). Default chords use Ctrl / Shift / Alt only.

## Reserved compositor keys (do not bind by default)

Super+Space, Super+Return (and Shift/Alt/Ctrl+Return), Super+W, Super+F, Super+T, Super+O, Super+P, Super+J, Super+C / V / X, Super+Ctrl+V, Super+K, Super+1–0, Super+Tab, Super+S, Super+Shift+Ctrl+A, Print / Super+Print family, Super+comma, Super+Escape, Super+Ctrl+L.

Save / undo / fit-view: Ctrl+S, Ctrl+Z, and a fit-view chord that is **not** Super+F.

## Acceptance tests

- App starts on Omarchy Wayland; docs do not require X11.
- `keymap --json` lists no default Super chord.
- While focused: Super+Space, Super+Return, Super+W, Super+F, Super+C/V/X still reach Hyprland (manual checklist until an automated compositor test exists).
- File picker via portal, not a raw X11 grab.
- Optional Hyprland window-rule snippet is **documentation**, never written to `~/.config/hypr/` by the tool.

XWayland-only is a defect if advertised as the Linux path. Wine is not the supported path.

## Upstream

File Wayland/shortcut defects on the GUI project (KiCad, FreeCAD, ParaView, PulseView). LET does not fork them for Super-key fights.

## License

N/A (contract). Incubated tools: Apache-2.0 unless matching an upstream license.
