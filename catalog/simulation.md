# Simulation free and open-source software (FOSS) on Linux

Finite element analysis (FEA), computational fluid dynamics (CFD), meshing, and related solvers. Contribute **upstream** before incubating. See [`SPACES.md`](../SPACES.md). Columns: [`README.md`](README.md). Terms: [`../TERMS.md`](../TERMS.md).

The Headless Core in the Omarchy extracts: these tools already run on Arch. LET glue is a CLI pipeline ([requirement #7](https://github.com/linux-engineering-tools/community/issues/7)), not a new solver.

## CFD (`domain:cfd`)

| Project | Job | Forge | Display |
|---|---|---|---|
| [OpenFOAM Foundation](https://openfoam.org/) | Finite-volume CFD (Foundation tree) | [GitHub](https://github.com/OpenFOAM/OpenFOAM-dev) | `cli` |
| [OpenFOAM (OpenCFD)](https://www.openfoam.com/) | Finite-volume CFD (OpenCFD / ESI tree) | [GitLab](https://gitlab.com/openfoam/core/openfoam) | `cli` |
| [SU2](https://su2code.github.io/) | CFD / design optimization (aerospace) | [GitHub](https://github.com/su2code/SU2) | `cli` |
| [Gmsh](https://gmsh.info/) | Mesh generation (also FEA) | [ONELAB GitLab](https://gitlab.onelab.info/gmsh/gmsh) | `unverified` |
| [Netgen](https://ngsolve.org/) | Tetrahedral meshing; NGSolve FEM | [GitHub](https://github.com/NGSolve/netgen) | `cli` |

The two OpenFOAM trees are not drop-in replacements. File issues on the tree the engineer actually runs.

## FEA / multiphysics (`domain:fea`)

| Project | Job | Forge | Display |
|---|---|---|---|
| [CalculiX](https://www.calculix.de/) | Structural FEA | [GitHub](https://github.com/Dhondtguido/CalculiX) | `cli` |
| [Code_Aster](https://code-aster.org/) | Structural / thermal FEA | [GitLab](https://gitlab.com/codeaster/src) | `cli` |
| [SALOME](https://www.salome-platform.org/) | CAD, mesh, and pre/post platform (Code_Aster stack) | [GitHub](https://github.com/SalomePlatform) | `unverified` |
| [Elmer](https://www.elmerfem.org/) | Multiphysics FEM | [GitHub](https://github.com/ElmerCSC/elmerfem) | `cli` |
| [deal.II](https://www.dealii.org/) | FEM library | [GitHub](https://github.com/dealii/dealii) | `cli` |

SALOME is the missing pre/post around Code_Aster. Do not incubate a SALOME replacement.

## Shared solvers / viz

| Project | Job | Forge | Display |
|---|---|---|---|
| [PETSc](https://petsc.org/) | Sparse solvers, nonlinear/time integrators | [GitLab](https://gitlab.com/petsc/petsc) | `cli` |
| [Trilinos](https://trilinos.github.io/) | HPC solver stack | [GitHub](https://github.com/trilinos/Trilinos) | `cli` |
| [Sundials](https://computing.llnl.gov/projects/sundials) | ODE/DAE integrators | [GitHub](https://github.com/LLNL/sundials) | `cli` |
| [VTK](https://vtk.org/) | Visualization library | [Kitware GitLab](https://gitlab.kitware.com/vtk/vtk) | `cli` |
| [ParaView](https://www.paraview.org/) | Visualization and post GUI | [Kitware GitLab](https://gitlab.kitware.com/paraview/paraview) | `xwayland` |

ParaView display evidence: [`desktop.md`](desktop.md).

Do not incubate a solver replacement. File LET requirements for **jobs** (open-format pre/post, Wayland-safe viz, fixture harnesses).
