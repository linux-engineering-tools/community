# Fabrication free and open-source software (FOSS) on Linux

Computer-aided manufacturing (CAM), computer numerical control (CNC) machine control, and 3D printing. Contribute **upstream** before incubating. See [`SPACES.md`](../SPACES.md). Columns: [`README.md`](README.md). Terms: [`../TERMS.md`](../TERMS.md).

`cam` is generating toolpaths from solids. `cnc` is running the machine. `print` is slice / host / firmware for additive.

## Toolpaths (`domain:cam`)

| Project | Job | Forge | Display |
|---|---|---|---|
| [FreeCAD](https://www.freecad.org/) CAM / Path | Toolpaths from CAD solids, G-code export | [GitHub](https://github.com/FreeCAD/FreeCAD) | `both` |
| [dxf2gcode](https://sourceforge.net/projects/dxf2gcode/) | 2D DXF/PDF/PS → G-code | [SourceForge](https://sourceforge.net/p/dxf2gcode/code/) | `unverified` |
| [LinuxCNC](https://linuxcnc.org/) docs/posts | Controller-side G-code dialect (not a CAM GUI) | [GitHub](https://github.com/LinuxCNC/linuxcnc) | `cli` |

Solid 3-axis mill and turning stay **upstream** in FreeCAD CAM ([requirement #4](https://github.com/linux-engineering-tools/community/issues/4)). Do not incubate a CAM GUI.

## G-code check (`domain:cam` / `cnc`)

| Project | Job | Forge | Display |
|---|---|---|---|
| [CAMotics](https://camotics.org/) | 3-axis G-code simulation and visualization on Linux | [GitHub](https://github.com/CauldronDevelopmentLLC/CAMotics) | `unverified` |

CAMotics is a simulator, not a toolpath generator.

## CNC control (`domain:cnc`)

| Project | Job | Forge | Display |
|---|---|---|---|
| [LinuxCNC](https://linuxcnc.org/) | Machine control, HAL, G-code interpreter | [GitHub](https://github.com/LinuxCNC/linuxcnc) | `unverified` |
| [Machinekit](https://www.machinekit.io/) | Related real-time motion (where still maintained) | [GitHub HAL](https://github.com/machinekit/machinekit-hal) | `cli` |
| [bCNC](https://github.com/vlachoudis/bCNC) | GRBL-class sender / pendant (Python) | [GitHub](https://github.com/vlachoudis/bCNC) | `unverified` |

LinuxCNC GUI notes: [`desktop.md`](desktop.md).

## 3D print (`domain:print`)

| Project | Job | Forge | Display |
|---|---|---|---|
| [PrusaSlicer](https://github.com/prusa3d/PrusaSlicer) | Slice to G-code | [GitHub](https://github.com/prusa3d/PrusaSlicer) | `unverified` |
| [OrcaSlicer](https://github.com/SoftFever/OrcaSlicer) | Slice (PrusaSlicer family) | [GitHub](https://github.com/SoftFever/OrcaSlicer) | `unverified` |
| [Cura](https://github.com/Ultimaker/Cura) | Slice | [GitHub](https://github.com/Ultimaker/Cura) | `unverified` |
| [Klipper](https://www.klipper3d.org/) | Printer firmware on a Linux host | [GitHub](https://github.com/Klipper3d/klipper) | `cli` |
| [Moonraker](https://moonraker.readthedocs.io/) | Klipper HTTP API | [GitHub](https://github.com/Arksine/moonraker) | `cli` |
| [Mainsail](https://docs.mainsail.xyz/) / [Fluidd](https://docs.fluidd.xyz/) | Printer web UI | [Mainsail](https://github.com/mainsail-crew/mainsail), [Fluidd](https://github.com/fluidd-core/fluidd) | `web` |
| [OctoPrint](https://octoprint.org/) | Printer host | [GitHub](https://github.com/OctoPrint/OctoPrint) | `web` |

Slicers and Klipper are the default homes. LET requirements should be **jobs** (CAD solid → slice with named profile, Wayland host UI with remappable keys, open G-code dialect tests), not a new slicer.
