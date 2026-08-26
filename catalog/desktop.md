# Desktop / Omarchy notes

Wayland notes for head-start GUIs. Not a ranking. The contract is [`../agents/skills/omarchy-desktop/SKILL.md`](../agents/skills/omarchy-desktop/SKILL.md) and [`../specs/omarchy-desktop/`](../specs/omarchy-desktop/).

These are **notes**, not test reports. Do not claim Omarchy verification unless it was run on that stack.

| Project | Toolkit (typical) | LET note |
|---|---|---|
| FreeCAD | Qt | Assemblies / TechDraw / CAM stay upstream (#2–#4). Super chords are compositor-owned. |
| KiCad | wx / GTK | PCB layout is served; Wayland and IPC-2581 jobs go **upstream** (#1, #15). |
| ParaView | Qt | Solver viz on Wayland without Super capture (#20). XWayland-only is a defect if claimed as the Linux path. |
| PulseView / SmuView | Qt | Bench GUIs wrap sigrok; new instrument support is libsigrok, not a LET GUI. |
| QGIS | Qt | GIS stays upstream (`catalog/civil.md`). |
| Blender / Bonsai | GTK / Blender | Mesh and IFC authoring; not a solids CAD. |

Wine or Proton is a compatibility footnote, never head-start OSS.

GUI tools LET might incubate later must wrap a CLI and follow the desktop spec. Do not bind Super by default.
