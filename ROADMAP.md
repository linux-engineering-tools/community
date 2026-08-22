# Roadmap from the Omarchy engineering-suite extracts

Research extracts (2026-08-21) in the Omarchy thought-process project converge on one architecture:

**Headless Core** (analysis, mesh, solve, script) is already strong on Linux.  
**Spatial Shell** (parametric geometry, BIM, high-end layout) is the bottleneck.  
**Greenfield** is a thin set: safety-certified automation, some regulatory biomedical/nuclear workflows, and a few interchange or high-frequency electronics jobs.

LET does **not** incubate a repo per catalog entry. Existing FOSS stays upstream (`catalog/`). New org repos wait on a spec + RFC (`agents/skills/incubate-tool/SKILL.md`).

This file is the fan-out: what to adopt, what to send upstream, and which **jobs** might later become LET tools.

## Classes

| Class | Meaning | LET action |
|---|---|---|
| **Head-start** | Linux-native OSS already does the job | Catalog + packaging/Wayland notes; patches **upstream** |
| **Fork-or-port** | Capability exists elsewhere or is incomplete on Linux | Prefer upstream or a documented port RFC; no silent forks |
| **Greenfield** | No reusable OSS kernel for the **job** | Requirement → spec → RFC → incubate |

TUI / library-first for solvers and pipelines. GUI only where spatial editing or map/schematic layout is the job. Shared kernels (OpenCASCADE, Gmsh, PETSc/Trilinos/Sundials, VTK, ngspice, HDF5, STEP/IFC) are dependencies, not LET products.

Compiled native tools (C, C++, Rust, Go) for anything LET incubates. No web-app-as-the-product.

## Adopt (do not rewrite)

Track on catalog pages. File LET issues only for **unmet jobs**.

| Domain | Head-start stack |
|---|---|
| Mechanical CAD | FreeCAD, SolveSpace, OpenSCAD, CadQuery, OpenCASCADE |
| Mesh / viz | Gmsh, Netgen, VTK, ParaView, Blender (mesh, not solids) |
| FEA | CalculiX, Code_Aster, Elmer |
| CFD | OpenFOAM, SU2 |
| Electronics (tier 1) | KiCad, Horizon EDA, LibrePCB, ngspice, Yosys, GHDL, Verilator, xschem |
| GIS / environment | QGIS, PDAL |
| Process / kinetics | DWSIM, COCO, Cantera |
| Scientific / HPC | PETSc, Trilinos, Octave, SciPy, Julia |
| Radiation (research) | OpenMC, Geant4 |
| Biomedical imaging (research) | DCMTK, Orthanc, PyDICOM, FSL |
| Fabrication | LinuxCNC, FreeCAD CAM, Klipper / PrusaSlicer family |
| Bench | sigrok, lxi-tools, OpenOCD |

## Send upstream first (already filed or to file)

These jobs should land in the named projects unless they decline.

| Job | Likely home | LET issue |
|---|---|---|
| Stable parametric assemblies | FreeCAD | #2 |
| Manufacturing drawings (ISO GPS / ASME Y14.5) | FreeCAD TechDraw | #3 |
| 3-axis mill / turning toolpaths | FreeCAD CAM | #4 |
| FEA/CFD CLI pre/post | CalculiX, Elmer, Code_Aster, OpenFOAM, Gmsh, FreeCAD FEM | #7 |
| STEP AP242 / DXF round-trip tests | OpenCASCADE, FreeCAD, plus a LET harness if needed | #8 |
| Geometry kernel reliability harness | OpenCASCADE / FreeCAD | #6 |
| PDM / BOM / revisions | InvenTree, Cascadia PLM | #5 |
| KiCad Wayland / Omarchy desktop | KiCad | (desktop #1) |
| IPC-2581 PCB manufacturing export | KiCad | new requirement |
| IFC structural round-trip | IfcOpenShell, Bonsai, FreeCAD Arch | new requirement |
| S-parameter / frequency-domain extraction | openEMS, scikit-rf, Qucs-S, ngspice | new requirement |
| ParaView / solver viz on Wayland | ParaView, VTK | new requirement |

## Candidate LET incubations (after spec + RFC)

Only if upstream is the wrong home. Not product clones.

| Working name | Job | GUI | Complexity | Shared libs |
|---|---|---|---|---|
| `let-interop` | Open-format round-trip test suite (STEP AP242, IFC, DXF, IPC-2581) | No | Medium | OpenCASCADE, IfcOpenShell |
| `let-solver-pipe` | One CLI to mesh → deck → run → JSON summary for existing solvers | No | Medium | Gmsh, VTK |
| `let-sparam` | Frequency-domain network extraction from an open EM/circuit model | No | High | openEMS / ngspice / HDF5 |
| `let-dexpi` | P&ID / process flowsheet on DEXPI / ISO 15926, TUI + optional canvas | Optional | High | — |
| `let-61131-test` | IEC 61131 / published safety-function **tests**, not a vendor runtime | No | High | OpenPLC / Beremiz if they accept it |
| `let-dicom-report` | Structure-set / dose summary from DICOM PS3 objects | No | Medium | DCMTK |

Do **not** incubate: a FreeCAD replacement, a KiCad replacement, an OpenFOAM replacement, a Blender replacement, a LabVIEW clone, a CATIA/NX clone, a Revit clone, or a Beckhoff runtime clone.

## Spatial-shell policy

Native Linux GUIs do not yet match high-fidelity parametric BIM or advanced surface modelling. LET treats:

- **Open interchange** (STEP, IFC, Gerber/IPC-2581) as the professional bar, not vendor binary editability (`.rvt`, `.pln`, `.adb`, `.nxasm`).
- Wine/Proton as a **compatibility footnote**, never as “head-start OSS.”
- New GUIs only with the Omarchy / Wayland contract (`agents/skills/omarchy-desktop/SKILL.md`).

## Sequence

1. Expand the catalog (this PR) so “does it exist?” is answered in-repo.
2. File remaining **requirements** in capability language (see below).
3. Write public **specs** for `let-interop` and `let-solver-pipe` (glue we can own).
4. RFC + incubate those two only after a maintainer decision.
5. Revisit greenfield rows when a space has a named maintainer.

## Requirement titles to file from this research

- `[req] IFC structural assembly round-trip on Linux`
- `[req] IPC-2581 PCB manufacturing interchange`
- `[req] Frequency-domain S-parameter extraction CLI`
- `[req] Process flowsheet on DEXPI or ISO 15926`
- `[req] Published-standard safety-function test harness`
- `[req] DICOM PS3 structure/dose summary CLI`
- `[req] Solver visualization on Wayland without Super-key capture`

Accountable human for agent-drafted items: @calledtoconstruct
