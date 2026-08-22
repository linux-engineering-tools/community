# Spec draft: `let-solver-pipe`

One **CLI pre/post pipeline** over **existing** FEA/CFD solvers. Not a new solver. Not a workbench clone.

**Status:** draft — tied to [requirement #7](https://github.com/linux-engineering-tools/community/issues/7). RFC before any repo.

## Job

Mesh a solid, write a solver deck, run or dry-run the solver, emit a JSON summary — without a GUI.

## Standards / formats

- Geometry in: STEP
- Mesh: Gmsh `.msh`
- Solvers (first): CalculiX, Elmer, OpenFOAM via **their** documented decks
- Results: VTK or solver-native open files; summary JSON (max displacement, residual, or equivalent)

## CLI (proposed)

Binary not named `let`. Example:

```
let-solver-pipe run --solver calculix --geom fixture.step --json summary.json
let-solver-pipe run --solver openfoam --case fixture-case --dry-run
```

Exit codes: 0 ok, 2 input/mesh error (file:line when possible), 3 solver failed, 4 summary mismatch vs fixture.

## Acceptance tests

- One FEA fixture and one CFD fixture in-tree.
- Dry-run validates deck without a long solve.
- JSON schema for the summary documented in this spec.

## Upstream check

FreeCAD FEM, CalculiX, OpenFOAM, Gmsh, ParaView. Prefer patches there. Incubate only as thin glue if they will not take a shared CLI contract.

## GUI

Optional later; must wrap this CLI. Omarchy desktop contract if GUI exists.

## License

Apache-2.0 if incubated.
