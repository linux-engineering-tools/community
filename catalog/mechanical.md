# Mechanical design FOSS on Linux

Parametric CAD, mesh modelling, and drawings. Contribute **upstream** before incubating. See [`SPACES.md`](../SPACES.md).

`cad` ≠ `mesh`. A solid with a feature history is not a triangle sculpture.

Kernels are dependencies, not LET products. Geometry reliability jobs go to the kernel or the CAD that embeds it ([requirement #6](https://github.com/linux-engineering-tools/community/issues/6)).

## Kernels (`domain:cad` / `interop`)

| Project | Job |
|---|---|
| [Open CASCADE Technology](https://dev.opencascade.org/) | B-rep solids, Booleans, STEP exchange (FreeCAD and others) |
| [Netgen](https://ngsolve.org/) | Tetrahedral meshing from solids / STL (also simulation) |

Do not incubate a kernel replacement.

## Parametric / solids (`domain:cad`)

| Project | Job |
|---|---|
| [FreeCAD](https://www.freecad.org/) | Parametric 3D CAD, assemblies, drawings, some CAM/FEM |
| [SolveSpace](https://solvespace.com/) | Constraint-based 3D CAD |
| [BRL-CAD](https://brlcad.org/) | Constructive solid geometry |
| [OpenSCAD](https://openscad.org/) | Programmatic solids |
| [CadQuery](https://cadquery.readthedocs.io/) | Programmatic CAD (Python) |
| [LibreCAD](https://librecad.org/) | 2D CAD |
| [QCAD](https://qcad.org/) | 2D CAD |

## Mesh / organic (`domain:mesh`)

| Project | Job |
|---|---|
| [Blender](https://www.blender.org/) | Mesh modelling, sculpt, rendering, some print helpers |
| [Wings 3D](http://www.wings3d.com/) | Subdivision modelling |
| [MeshLab](https://www.meshlab.net/) | Mesh repair and inspection |

Do not incubate a Blender replacement. File LET requirements only for **jobs** Blender/FreeCAD will not take (for example a specific engineering mesh-repair CLI with fixtures).

## Drawings (`domain:drawings`)

FreeCAD TechDraw is the default upstream. See the drawings requirement issues.
