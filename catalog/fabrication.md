# Fabrication FOSS on Linux

CAM, CNC machine control, and 3D printing. Contribute **upstream** before incubating. See [`SPACES.md`](../SPACES.md).

`cam` is generating toolpaths from solids. `cnc` is running the machine. `print` is slice / host / firmware for additive.

## Toolpaths (`domain:cam`)

| Project | Job |
|---|---|
| FreeCAD CAM / Path | Toolpaths from CAD, G-code export |
| [LinuxCNC](https://linuxcnc.org/) docs/posts | Controller-side G-code (not a CAM GUI) |

## CNC control (`domain:cnc`)

| Project | Job |
|---|---|
| [LinuxCNC](https://linuxcnc.org/) | Machine control, HAL, G-code interpreter |
| [Machinekit](https://www.machinekit.io/) | Related real-time motion (where still maintained) |

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

Slicers and Klipper are the default homes. LET requirements should be **jobs** (CAD solid → slice with named profile, Omarchy-friendly host UI, open G-code dialect tests), not a new slicer.
