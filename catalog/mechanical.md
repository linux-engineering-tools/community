# Mechanical design free and open-source software (FOSS) on Linux

Parametric computer-aided design (CAD), mesh modelling, and drawings. Contribute **upstream** before incubating. See [`SPACES.md`](../SPACES.md). Columns: [`README.md`](README.md). Terms: [`../TERMS.md`](../TERMS.md).

`cad` ≠ `mesh`. A solid with a feature history is not a triangle sculpture.

Kernels are dependencies, not LET products. Geometry reliability jobs go to the kernel or the CAD that embeds it ([requirement #6](https://github.com/linux-engineering-tools/community/issues/6)).

## Kernels (`domain:cad` / `interop`)

| Project | Job | Forge | Display |
|---|---|---|---|
| [Open CASCADE Technology](https://dev.opencascade.org/) | B-rep solids, Booleans, STEP exchange (FreeCAD and others) | [GitHub](https://github.com/Open-Cascade-SAS/OCCT) | `cli` |
| [Netgen](https://ngsolve.org/) | Tetrahedral meshing from solids / STL (also simulation) | [GitHub](https://github.com/NGSolve/netgen) | `cli` |

Do not incubate a kernel replacement.

## Parametric / solids (`domain:cad`)

| Project | Job | Forge | Display |
|---|---|---|---|
| [FreeCAD](https://www.freecad.org/) | Parametric 3D CAD, assemblies, drawings, some CAM/FEM | [GitHub](https://github.com/FreeCAD/FreeCAD) | `both` |
| [SolveSpace](https://solvespace.com/) | Constraint-based 3D CAD | [GitHub](https://github.com/solvespace/solvespace) | `unverified` |
| [BRL-CAD](https://brlcad.org/) | Constructive solid geometry | [GitHub](https://github.com/BRL-CAD/brlcad) | `unverified` |
| [OpenSCAD](https://openscad.org/) | Programmatic solids | [GitHub](https://github.com/openscad/openscad) | `unverified` |
| [CadQuery](https://cadquery.readthedocs.io/) | Programmatic CAD (Python) | [GitHub](https://github.com/CadQuery/cadquery) | `cli` |
| [LibreCAD](https://librecad.org/) | 2D CAD | [GitHub](https://github.com/LibreCAD/LibreCAD) | `unverified` |
| [QCAD](https://qcad.org/) | 2D CAD | [GitHub](https://github.com/qcad/qcad) | `unverified` |

GUI display notes: [`desktop.md`](desktop.md).

## Mesh / organic (`domain:mesh`)

| Project | Job | Forge | Display |
|---|---|---|---|
| [Blender](https://www.blender.org/) | Mesh modelling, sculpt, rendering, some print helpers | [Gitea](https://projects.blender.org/blender/blender) | `both` |
| [Wings 3D](http://www.wings3d.com/) | Subdivision modelling | [GitHub](https://github.com/dgud/wings) | `unverified` |
| [MeshLab](https://www.meshlab.net/) | Mesh repair and inspection | [GitHub](https://github.com/cnr-isti-vclab/meshlab) | `unverified` |

Do not incubate a Blender replacement. File LET requirements only for **jobs** Blender/FreeCAD will not take (for example a specific engineering mesh-repair CLI with fixtures).

## Drawings (`domain:drawings`)

FreeCAD TechDraw is the default upstream. See the drawings requirement issues.
