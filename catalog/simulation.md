# Simulation free and open-source software (FOSS) on Linux

Finite element analysis (FEA), computational fluid dynamics (CFD), meshing, and related solvers. Contribute **upstream** before incubating. See [`SPACES.md`](../SPACES.md). Terms: [`../TERMS.md`](../TERMS.md).

The Headless Core in the Omarchy extracts: these tools already run on Arch. LET glue is a CLI pipeline ([requirement #7](https://github.com/linux-engineering-tools/community/issues/7)), not a new solver.

## CFD (`domain:cfd`)

| Project | Job |
|---|---|
| [OpenFOAM](https://openfoam.org/) | Finite-volume CFD |
| [SU2](https://su2code.github.io/) | CFD / design optimization (aerospace) |
| [Gmsh](https://gmsh.info/) | Mesh generation (also FEA) |
| [Netgen](https://ngsolve.org/) | Tetrahedral meshing; NGSolve FEM |

## FEA / multiphysics (`domain:fea`)

| Project | Job |
|---|---|
| [CalculiX](https://www.calculix.de/) | Structural FEA |
| [Code_Aster](https://code-aster.org/) | Structural / thermal FEA |
| [Elmer](https://www.elmerfem.org/) | Multiphysics FEM |
| [deal.II](https://www.dealii.org/) | FEM library |

## Shared solvers / viz

| Project | Job |
|---|---|
| [PETSc](https://petsc.org/) | Sparse solvers, nonlinear/time integrators |
| [Trilinos](https://trilinos.github.io/) | HPC solver stack |
| [Sundials](https://computing.llnl.gov/projects/sundials) | ODE/DAE integrators |
| [VTK](https://vtk.org/) / [ParaView](https://www.paraview.org/) | Visualization and post |

Do not incubate a solver replacement. File LET requirements for **jobs** (open-format pre/post, Wayland-safe viz, fixture harnesses).
