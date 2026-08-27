# Terms

Legend for this project. Other pages should **spell the term out on first use**, then use the short form. This file is the index if you land mid-document.

Linux Engineering Tools (LET) is a **requirements and incubation** board, not a textbook. Definitions here are working senses, not legal or standards-body substitutes.

## Project process

| Term | Meaning here |
|---|---|
| **LET** | Linux Engineering Tools — this organization. |
| **Capability / job to be done** | What an engineer must finish (inputs, outputs, tests). Not a request to copy a named commercial product. |
| **Requirement** | A GitHub issue describing that job. Use the Requirement form. |
| **RFC** | Request for comments — a GitHub issue proposing to incubate a new repo or change process. |
| **Spec** | A public specification under `specs/` (job, standards, command-line interface, tests). Required before a new tool repo. |
| **Upstream** | An existing project that should own the work. Prefer patches there. |
| **Incubate** | Create a new repository under this organization after a spec and an RFC. Last resort. |
| **Clean room** | Implement from public specs and standards, not from proprietary source, leaked manuals, or decompiled binaries. |
| **FOSS** | Free and open-source software. |
| **DCO** | Developer Certificate of Origin — every commit has `Signed-off-by: Name <email>`. |
| **Space** | A topic area (Mechanical, Fabrication, …): discussion category + labels. Not a separate GitHub organization. |
| **Domain** | Fine-grained issue label (`cad`, `print`, `bench`, …). |
| **Fixture** | An in-tree sample file used as a test input (open formats only). |
| **CLI** | Command-line interface — a program you run in a terminal, with `--help` and exit codes. |
| **GUI** | Graphical user interface — windows, pointing, drawing. |
| **TUI** | Text user interface — interactive terminal screens. |
| **CI** | Continuous integration — automated tests on each change. |
| **JSON** | JavaScript Object Notation — structured text for machine-readable reports. |

## Mechanical, geometry, drawings

| Term | Meaning here |
|---|---|
| **CAD** | Computer-aided design — building a precise 3D (or 2D) model of a part or assembly. |
| **Parametric CAD** | The model is driven by a history of features and dimensions that can be changed and rebuilt (`domain:cad`). |
| **Mesh / organic modelling** | The model is polygons, sculpt, or subdivision surfaces (`domain:mesh`). Not the same job as parametric solids. |
| **Kernel** | The geometry library a CAD program uses for solids and Booleans (here, usually Open CASCADE Technology). |
| **OCCT** | Open CASCADE Technology — open-source 3D modelling kernel used by FreeCAD and others. |
| **B-rep** | Boundary representation — a solid described by its faces, edges, and vertices. |
| **STEP** | ISO 10303 file format for exchanging 3D product data. **AP242** (application protocol 242) is the assembly-oriented flavour we prefer; AP214 is a documented fallback. |
| **DXF** | Drawing Exchange Format — 2D drawing interchange (published Autodesk spec). |
| **Round-trip** | Export a file, import it again, and check that counts, units, and bounds still match within a stated tolerance. |
| **ISO GPS** | ISO geometrical product specifications — how dimensions and tolerances are stated on drawings. |
| **ASME Y14.5** | U.S. dimensioning and tolerancing standard. |

## Fabrication

| Term | Meaning here |
|---|---|
| **CAM** | Computer-aided manufacturing — generating **toolpaths** from a solid or drawing (`domain:cam`). |
| **CNC** | Computer numerical control — running the machine from those paths (`domain:cnc`). |
| **G-code** | Numeric control language sent to mills, lathes, and many 3D printers (dialects vary; LinuxCNC is documented here). |
| **Post-processor** | A translator from a generic toolpath to a specific machine’s G-code dialect. |
| **Slicer** | Program that turns a 3D-print model into layer G-code (`domain:print`). |
| **Host (print)** | Software that talks to the printer (queue, temperature, start/stop). |

## Electronics

| Term | Meaning here |
|---|---|
| **EDA** | Electronic design automation — schematic and printed circuit board layout (`domain:eda`). |
| **PCB** | Printed circuit board. |
| **Gerber / Excellon** | Common fabrication outputs for copper layers and drill files. **Gerber X3** is a recent Gerber flavour. |
| **IPC-2581** | Published PCB manufacturing interchange (preferred over vendor CAM databases). |
| **Netlist** | List of electrical connections between pins. |
| **SCPI** | Standard Commands for Programmable Instruments (IEEE 488.2 style text over LAN, USB, or GPIB). |
| **LXI** | LAN eXtensions for Instrumentation — instruments on Ethernet. |
| **USBTMC** | USB Test and Measurement Class. |
| **GPIB** | General Purpose Interface Bus (IEEE 488.1). |
| **JTAG / SWD** | Debug and programming interfaces for microcontrollers (Joint Test Action Group; Serial Wire Debug). |
| **S-parameter** | Scattering parameter — frequency-domain description of how a network reflects and transmits signals. |
| **Touchstone / SnP** | File format for S-parameters. |

## Simulation

| Term | Meaning here |
|---|---|
| **FEA** | Finite element analysis — structural / thermal (and related) numerical simulation (`domain:fea`). |
| **CFD** | Computational fluid dynamics (`domain:cfd`). |
| **Pre/post** | Prepare a mesh and boundary conditions (pre); inspect results (post). |
| **Deck** | A solver’s input files (CalculiX, Elmer, OpenFOAM, and similar). |
| **VTK** | Visualization Toolkit — common open result/mesh files; **ParaView** is a GUI for them. |
| **Dry-run** | Validate inputs without a long solve or a kernel export. |

## Data, buildings, maps

| Term | Meaning here |
|---|---|
| **PDM** | Product data management — revisions, check-in/out, change records (`domain:pdm`). |
| **PLM** | Product lifecycle management — broader than PDM (BOM, changes, effectivity). |
| **BOM** | Bill of materials — parts list with quantities. |
| **Interop** | Interoperability — open formats moving between tools without silent loss (`domain:interop`). |
| **IFC** | Industry Foundation Classes (ISO 16739) — open building/structural model. |
| **BIM** | Building information modelling. |
| **GIS** | Geographic information system — maps and geospatial data. |

## Process, automation, scientific

| Term | Meaning here |
|---|---|
| **DEXPI / ISO 15926** | Published information models for process plants (piping and instrumentation / lifecycle data). |
| **P&ID** | Piping and instrumentation diagram. |
| **IEC 61131-3** | Standard languages for programmable controllers (we start with Structured Text). |
| **OPC UA** | Open Platform Communications Unified Architecture — industrial data exchange. |
| **EtherCAT** | Ethernet-based fieldbus for motion and I/O. |
| **SIL** | Safety integrity level — a *claim* in documentation, not a LET certification mark. |
| **DICOM** | Digital Imaging and Communications in Medicine. **PS3** is the published DICOM standard. |
| **HPC** | High-performance computing. |

## Desktop

| Term | Meaning here |
|---|---|
| **Wayland** | Modern Linux display protocol. An **X11-only** path is not the supported Linux path here. |
| **Omarchy** | Arch Linux desktop distribution using **Hyprland** (a Wayland compositor). A test desktop for LET graphical tools, and the example of simple keybinding config files. |
| **Super key** | The key often labelled with a logo (Windows / Command / Super). Most Linux desktops already use it. LET defaults use Ctrl / Shift / Alt; users remap via a keybinding file if a chord still collides. |
| **Keybinding file** | A small user-editable text or JSON file that maps actions to chords. Omarchy's `~/.config/hypr/bindings.lua` is the example of this style. |
| **HiDPI** | High pixel-density displays; apps should follow session scale. |
| **Wine / Proton** | Windows compatibility layers. A footnote, never “the Linux version.” |

## File extensions we refuse as the spec

`.rvt`, `.pln`, `.adb`, `.nxasm` and similar **vendor binaries** are out of scope. The professional bar is published formats (STEP, IFC, DXF, Gerber, IPC-2581, and so on).
