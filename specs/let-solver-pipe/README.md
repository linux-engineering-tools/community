# Spec: `let-solver-pipe`

One **command-line interface (CLI) prepare/inspect pipeline** over **existing** finite element analysis (FEA) and computational fluid dynamics (CFD) solvers. Not a new solver. Not a workbench clone. Terms: [`../../TERMS.md`](../../TERMS.md).

**Status:** draft — requirement [#7](https://github.com/linux-engineering-tools/community/issues/7). RFC [#22](https://github.com/linux-engineering-tools/community/issues/22). **Do not create a repo** until upstream is asked and a maintainer accepts the RFC.

## Job

Mesh a solid, write a solver deck, run or dry-run the solver, emit a JSON summary — without a GUI.

## Standards / formats

- Geometry in: STEP
- Mesh: Gmsh `.msh`
- Solvers (first): CalculiX, Elmer, OpenFOAM via **their** documented decks
- Results: VTK or solver-native open files; summary JSON

## CLI (proposed)

Binary not named `let`.

```
let-solver-pipe --help
let-solver-pipe run --solver calculix --geom fixtures/fea/cantilever.step --json summary.json
let-solver-pipe run --solver openfoam --case fixtures/cfd/lid-cavity --dry-run --json summary.json
```

`--dry-run` writes or validates the deck and mesh, prints JSON, and does **not** start a long solve.

### Exit codes

| Code | Meaning |
|---|---|
| 0 | Ok (including successful dry-run) |
| 2 | Input / mesh error (`error.file` + `error.line` when the engine provides them) |
| 3 | Solver failed (non-zero from the engine) |
| 4 | Summary mismatch vs fixture expect JSON |
| 64 | Usage |

## JSON summary

Schema: [`summary.schema.json`](summary.schema.json). Required: `ok`, `solver`, `dry_run`. FEA fixtures include `max_displacement`. CFD fixtures include `residual` (or the engine’s equivalent documented field).

## Fixtures

[`fixtures/README.md`](fixtures/README.md). One FEA, one CFD. Public geometry only.

## Acceptance tests

- FEA fixture: STEP → mesh → CalculiX or Elmer deck → `--dry-run` exits 0; JSON names the solver.
- CFD fixture: OpenFOAM case → `--dry-run` validates; JSON `ok: true`.
- Optional live solve is not required in CI (too long / too many packages). Document `LET_SOLVER_LIVE=1` for a local run.
- Failures name the solver in `error.solver`.
- Headless.

## Upstream check

Prefer FreeCAD FEM, CalculiX, Elmer, Code_Aster, OpenFOAM, Gmsh. Incubate only as thin glue if they will not take a shared CLI contract.

Asks: [`upstream-ask.md`](upstream-ask.md). Record URLs on RFC #22.

## GUI

Optional later; must wrap this CLI. Omarchy contract if a GUI exists ([`../omarchy-desktop/`](../omarchy-desktop/)).

## License

Apache-2.0 if incubated.
