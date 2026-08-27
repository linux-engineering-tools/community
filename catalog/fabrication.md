# Fabrication free and open-source software (FOSS) on Linux

Computer-aided manufacturing (CAM), computer numerical control (CNC) machine control, and 3D printing. Contribute **upstream** before incubating. See [`SPACES.md`](../SPACES.md). Terms: [`../TERMS.md`](../TERMS.md).

`cam` is generating toolpaths from solids. `cnc` is running the machine. `print` is slice / host / firmware for additive.

## Toolpaths (`domain:cam`)

| Project | Job |
|---|---|
| [FreeCAD](https://www.freecad.org/) CAM / Path | Toolpaths from CAD solids, G-code export |
| [dxf2gcode](https://sourceforge.net/projects/dxf2gcode/) | 2D DXF/PDF/PS → G-code |
| [LinuxCNC](https://linuxcnc.org/) docs/posts | Controller-side G-code dialect (not a CAM GUI) |

Solid 3-axis mill and turning stay **upstream** in FreeCAD CAM ([requirement #4](https://github.com/linux-engineering-tools/community/issues/4)). Do not incubate a CAM GUI.

## G-code check (`domain:cam` / `cnc`)

| Project | Job |
|---|---|
| [CAMotics](https://camotics.org/) | 3-axis G-code simulation and visualization on Linux |

CAMotics is a simulator, not a toolpath generator.

## CNC control (`domain:cnc`)

| Project | Job |
|---|---|
| [LinuxCNC](https://linuxcnc.org/) | Machine control, HAL, G-code interpreter |
| [Machinekit](https://www.machinekit.io/) | Related real-time motion (where still maintained) |
| [bCNC](https://github.com/vlachoudis/bCNC) | GRBL-class sender / pendant (Python) |

## 3D print (`domain:print`)

| Project | Job |
|---|---|
| [PrusaSlicer](https://github.com/prusa3d/PrusaSlicer) | Slice to G-code |
| [OrcaSlicer](https://github.com/SoftFever/OrcaSlicer) | Slice (PrusaSlicer family) |
| [Cura](https://github.com/Ultimaker/Cura) | Slice |
| [Klipper](https://www.klipper3d.org/) | Printer firmware on a Linux host |
| [Moonraker](https://moonraker.readthedocs.io/) | Klipper HTTP API |
| [Mainsail](https://docs.mainsail.xyz/) / [Fluidd](https://docs.fluidd.xyz/) | Printer web UI |
| [OctoPrint](https://octoprint.org/) | Printer host |

Slicers and Klipper are the default homes. LET requirements should be **jobs** (CAD solid → slice with named profile, Wayland host UI with remappable keys, open G-code dialect tests), not a new slicer.
