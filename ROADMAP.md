# Roadmap from the Omarchy engineering-suite extracts

Research extracts (2026-08-21) in the Omarchy thought-process project converge on one architecture. Terms: [`TERMS.md`](TERMS.md).

**Headless Core** (analysis, mesh, solve, script) is already strong on Linux.  
**Spatial Shell** (parametric geometry, building information modelling (BIM), high-end layout) is the bottleneck.  
**Greenfield** is a thin set: safety-certified automation, some regulatory biomedical/nuclear workflows, and a few interchange or high-frequency electronics jobs.

Linux Engineering Tools (LET) does **not** incubate a repo per catalog entry. Existing free and open-source software (FOSS) stays **upstream** (`catalog/`). New org repos wait on a specification plus a request for comments (RFC) (`agents/skills/incubate-tool/SKILL.md`).

This file is the fan-out: what to adopt, what to send upstream, and which **jobs** might later become LET tools.

Accountable human for agent-drafted items: [@calledtoconstruct](https://github.com/calledtoconstruct).

## Classes

| Class | Meaning | LET action |
|---|---|---|
| **Head-start** | Linux-native OSS already does the job | Catalog + packaging/Wayland notes; patches **upstream** |
| **Fork-or-port** | Capability exists elsewhere or is incomplete on Linux | Prefer upstream or a documented port RFC; no silent forks |
| **Greenfield** | No reusable OSS kernel for the **job** | Requirement → spec → RFC → incubate |

Text user interface (TUI) / library-first for solvers and pipelines. Graphical user interface (GUI) only where spatial editing or map/schematic layout is the job. Shared kernels (Open CASCADE Technology, Gmsh, PETSc/Trilinos/Sundials, Visualization Toolkit (VTK), ngspice, HDF5, ISO 10303 STEP / Industry Foundation Classes (IFC)) are dependencies, not LET products.

Compiled native tools (C, C++, Rust, Go) for anything LET incubates. No web-app-as-the-product.

## Adopt (do not rewrite)

Track on catalog pages. File LET issues only for **unmet jobs**.

| Domain | Head-start stack | Catalog |
|---|---|---|
| Mechanical CAD | FreeCAD, SolveSpace, OpenSCAD, CadQuery, OpenCASCADE | [`catalog/mechanical.md`](catalog/mechanical.md) |
| Mesh / viz | Gmsh, Netgen, VTK, ParaView, Blender (mesh, not solids) | mechanical + [`catalog/simulation.md`](catalog/simulation.md) |
| FEA | CalculiX, Code_Aster, SALOME, Elmer | simulation |
| CFD | OpenFOAM Foundation, OpenFOAM OpenCFD, SU2 | simulation |
| Electronics (tier 1) | KiCad, Horizon EDA, LibrePCB, ngspice, Yosys, GHDL, Verilator, xschem, openEMS | [`catalog/electronics.md`](catalog/electronics.md) |
| GIS / environment | QGIS, PDAL, GDAL | [`catalog/civil.md`](catalog/civil.md) |
| Process / kinetics | DWSIM, COCO, Cantera | [`catalog/process.md`](catalog/process.md) |
| Scientific / HPC | PETSc, Trilinos, Octave, SciPy, Julia | [`catalog/scientific.md`](catalog/scientific.md) |
| Radiation (research) | OpenMC, Geant4 | scientific |
| Biomedical imaging (research) | DCMTK, Orthanc, PyDICOM, FSL | scientific |
| Fabrication | LinuxCNC, FreeCAD CAM, CAMotics, Klipper / PrusaSlicer family | [`catalog/fabrication.md`](catalog/fabrication.md) |
| Bench | sigrok, lxi-tools, OpenOCD | electronics |
| Data / PDM | InvenTree, Cascadia PLM, Part-DB | [`catalog/data.md`](catalog/data.md) |
| Desktop | Omarchy / Wayland notes | [`catalog/desktop.md`](catalog/desktop.md) |

## Send upstream first (filed)

These jobs should land in the named projects unless they decline.

| Job | Likely home | LET issue | Stage |
|---|---|---|---|
| Wayland GUI contract (remappable keybindings) | Each GUI project; LET spec | #1 | needs-spec ([spec](specs/omarchy-desktop/)) |
| Stable parametric assemblies | FreeCAD | #2 | upstream-first |
| Manufacturing drawings (ISO GPS / ASME Y14.5) | FreeCAD TechDraw | #3 | upstream-first |
| 3-axis mill / turning toolpaths | FreeCAD CAM | #4 | upstream-first |
| PDM / BOM / revisions | InvenTree, Cascadia PLM | #5 | upstream-first |
| Geometry kernel reliability harness | OpenCASCADE / FreeCAD | #6 | needs-spec ([spec](specs/geometry-harness/)) |
| FEA/CFD CLI pre/post | CalculiX, Elmer, Code_Aster, OpenFOAM, Gmsh, FreeCAD FEM | #7 | upstream-first ([spec](specs/let-solver-pipe/), RFC #22) |
| STEP AP242 / DXF round-trip tests | OpenCASCADE, FreeCAD, plus a LET harness if needed | #8 | needs-spec ([spec](specs/let-interop/), RFC #21) |
| Instrument identity map | sigrok, lxi-tools, catalog | #10 | needs-spec ([spec](specs/instrument-map/)) |
| Time-aligned PSU + DMM log | sigrok, lxi-tools | #11 | upstream-first |
| USB host capture workflow | usbmon, Wireshark | #12 | upstream-first |
| IFC parse + IfcDiff (geometry rewrite in Bonsai) | IfcOpenShell, Bonsai | #14 | upstream-first |
| IPC-2581 PCB manufacturing export | KiCad | #15 | upstream-first |
| S-parameter / frequency-domain extraction | openEMS, scikit-rf, Qucs-S, ngspice | #16 | upstream-first |
| Process flowsheet on DEXPI / ISO 15926 | DWSIM, COCO | #17 | needs-spec |
| IEC 61131 safety-function **tests** | OpenPLC, Beremiz | #18 | upstream-first |
| DICOM structure/dose summary | DCMTK, Orthanc | #19 | upstream-first |
| ParaView / solver viz on Wayland | ParaView, VTK | #20 | upstream-first |

RFCs [#21](https://github.com/linux-engineering-tools/community/issues/21) (`let-interop`) and [#22](https://github.com/linux-engineering-tools/community/issues/22) (`let-solver-pipe`): asks posted. Replies so far: IfcOpenShell (parse + IfcDiff, not native-model round-trip), FreeCAD FEM (`FreeCADCmd script.py`, not argv). OCCT assigned, no comment. Elmer silent. Details in each spec's `upstream-ask.md`.

## Candidate LET incubations (after spec + RFC)

Only if upstream is the wrong home. Not product clones. **No empty tool repositories.**

| Working name | Job | GUI | Spec | RFC |
|---|---|---|---|---|
| `let-interop` | Open-format round-trip test suite | No | [specs/let-interop](specs/let-interop/) | #21 **incubating** ([repo](https://github.com/linux-engineering-tools/let-interop)) |
| `let-solver-pipe` | Mesh → deck → run → JSON over existing solvers | No | [specs/let-solver-pipe](specs/let-solver-pipe/) | #22 |
| `let-sparam` | Frequency-domain network extraction | No | — (stay on #16) | — |
| `let-dexpi` | P&ID / flowsheet on DEXPI / ISO 15926 | Optional | — (stay on #17) | — |
| `let-61131-test` | IEC 61131 published-function **tests** | No | — (stay on #18) | — |
| `let-dicom-report` | Structure-set / dose summary from DICOM PS3 | No | — (stay on #19) | — |

Do **not** incubate: a FreeCAD replacement, a KiCad replacement, an OpenFOAM replacement, a Blender replacement, a LabVIEW clone, a CATIA/NX clone, a Revit clone, or a Beckhoff runtime clone.

## Spatial-shell policy

Native Linux GUIs do not yet match high-fidelity parametric BIM or advanced surface modelling. LET treats:

- **Open interchange** (STEP, IFC, Gerber/IPC-2581) as the professional bar, not vendor binary editability (`.rvt`, `.pln`, `.adb`, `.nxasm`).
- Wine/Proton as a **compatibility footnote**, never as “head-start OSS.”
- New GUIs only with the desktop contract: Wayland, plus a user-editable keybinding file (`agents/skills/omarchy-desktop/SKILL.md`, [`specs/omarchy-desktop/`](specs/omarchy-desktop/)).

## Sequence

1. Expand the catalog so “does it exist?” is answered in-repo. **Done** (including data, desktop, CAM sim, kernels). Forge and Display columns, GitLab/Kitware/ONELAB/Savannah scan list, SALOME, and the two OpenFOAM trees: [`catalog/README.md`](catalog/README.md).
2. File remaining **requirements** in capability language. **Done** (#14–#20). Stop filing more until these are triaged.
3. Write public **specs** for glue we might own (`let-interop`, `let-solver-pipe`) plus #1 / #6 / #10. **Drafts in `specs/`.**
4. **Ask upstream** using `specs/*/upstream-ask.md`. Record URLs on RFC #21 and #22. **Posted.** IfcOpenShell and FreeCAD FEM replies incorporated in the specs.
5. RFC + incubate those two **only** after a maintainer decision and a documented upstream answer (or timeout). **`let-interop` is incubating** (docs-first). `let-solver-pipe` is not.
6. Revisit greenfield rows (`let-sparam`, `let-dexpi`, `let-61131-test`, `let-dicom-report`) when a space has a named maintainer.

The GitHub project [Requirements](https://github.com/orgs/linux-engineering-tools/projects/1) is the board. **Status** stays Todo until a human is implementing. **Stage** is the pipeline. The project Domain field has no `process` / `automation` options yet; those issues use Domain `other` plus issue labels.
