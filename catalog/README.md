# Existing FOSS (contribute here first)

LET does not replace these. File an LET requirement only if the job is still unmet after considering them. Prefer patches and specs sent **upstream**.

This list is a map, not an endorsement ranking. Add entries with a name, what job they cover, and a URL.

## Mechanical / 3D CAD

| Project | Job |
|---|---|
| [FreeCAD](https://www.freecad.org/) | Parametric 3D CAD, assemblies, drawings, some CAM/FEM |
| [SolveSpace](https://solvespace.com/) | Constraint-based 3D CAD |
| [BRL-CAD](https://brlcad.org/) | Constructive solid geometry, analysis |
| [OpenSCAD](https://openscad.org/) | Programmatic solid modeling |
| [CadQuery](https://cadquery.readthedocs.io/) | Programmatic CAD (Python) |
| [LibreCAD](https://librecad.org/) | 2D CAD |
| [QCAD](https://qcad.org/) | 2D CAD (community / professional editions) |

## Electronics (EDA, bench, repair)

Design tools (KiCad and friends), instrument control (sigrok, LXI/SCPI), USB capture, and JTAG/SWD are listed in [`electronics.md`](electronics.md). The usual problem is **finding** them, not that none exist. Read that page before filing a `domain:eda` or `domain:bench` requirement.

## Simulation

| Project | Job |
|---|---|
| [OpenFOAM](https://openfoam.org/) | CFD |
| [CalculiX](https://www.calculix.de/) | FEA |
| [Code_Aster](https://code-aster.org/) | FEA |
| [Elmer](https://www.elmerfem.org/) | Multiphysics FEM |
| [Gmsh](https://gmsh.info/) | Mesh generation |

## Manufacturing

| Project | Job |
|---|---|
| [LinuxCNC](https://linuxcnc.org/) | CNC machine control |
| FreeCAD CAM / Path | Toolpath generation from CAD |

## PDM / inventory

| Project | Job |
|---|---|
| [InvenTree](https://inventree.org/) | Parts, stock, BOM |
| [Cascadia PLM](https://cascadiaplm.com/) | Self-hosted PLM |

## Scientific computing

| Project | Job |
|---|---|
| [GNU Octave](https://octave.org/) | Numerical computing |
| [NumPy / SciPy](https://scipy.org/) | Numerical computing in Python |
| [Julia](https://julialang.org/) | Numerical / scientific computing |

If you add a project, link the upstream contribution guide from the LET issue that should go there.
