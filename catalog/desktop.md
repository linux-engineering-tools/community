# Desktop / Omarchy notes

Wayland notes for head-start graphical user interfaces (GUIs). Not a ranking. The contract is [`../agents/skills/omarchy-desktop/SKILL.md`](../agents/skills/omarchy-desktop/SKILL.md) and [`../specs/omarchy-desktop/`](../specs/omarchy-desktop/). Display tokens: [`README.md`](README.md). Terms: [`../TERMS.md`](../TERMS.md).

These are **notes**, not test reports. Do not claim Omarchy verification unless it was run on that stack.

| Project | Toolkit (typical) | Display | Evidence | LET note |
|---|---|---|---|---|
| FreeCAD | Qt | `both` | [1.1 blog](https://blog.freecad.org/2026/03/25/freecad-version-1-1-released/) and [release notes](https://wiki.freecad.org/Release_notes_1.1) (Wayland fixes; X11 remains) | Assemblies / TechDraw / CAM stay upstream (#2–#4). Shortcuts should be remappable in a simple config file. |
| KiCad | wx / GTK | `x11` | [KiCad and Wayland Support](https://www.kicad.org/blog/2025/06/KiCad-and-Wayland-Support/) (2025-06: use X11) | PCB layout is served; Wayland and IPC-2581 jobs go **upstream** (#1, #15). Forge is [GitLab](https://gitlab.com/kicad/code/kicad), not the GitHub mirror. |
| ParaView | Qt | `xwayland` | [ParaView 6 on Ubuntu 24.04 with Wayland](https://discourse.paraview.org/t/install-paraview-6-on-ubuntu-24-04-with-wayland/17179) (2025-09: no native Wayland) | Solver viz on Wayland without capturing the desktop's Super key by default (#20). XWayland-only is a defect if claimed as the Linux path. Forge is [Kitware GitLab](https://gitlab.kitware.com/paraview/paraview). |
| PulseView / SmuView | Qt | `unverified` | none | Bench GUIs wrap sigrok; new instrument support is libsigrok, not a LET GUI. |
| QGIS | Qt | `unverified` | none | GIS stays upstream (`catalog/civil.md`). |
| Blender / Bonsai | GTK / Blender | `both` | [Wayland Support on Linux](https://code.blender.org/2022/10/wayland-support-on-linux/) | Mesh and IFC authoring; not a solids CAD. Forge is [projects.blender.org](https://projects.blender.org/blender/blender). |
| SALOME | Qt | `unverified` | none | Pre/post around Code_Aster. Stays upstream (`catalog/simulation.md`). |
| LinuxCNC (AXIS and similar) | Tk / GTK | `unverified` | none | Machine control. Tk paths are usually X11; do not treat that as a LET GUI contract until measured. |

Wine or Proton is a compatibility footnote, never head-start OSS.

GUI tools LET might incubate later must wrap a CLI and follow the desktop spec. Ship a user-editable keybinding file. Do not bind Super by default.
