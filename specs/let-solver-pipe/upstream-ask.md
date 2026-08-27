# Upstream asks (copy-paste)

Record URLs on [RFC #22](https://github.com/linux-engineering-tools/community/issues/22) before incubating.

## Shared question

We want one **headless** path on Linux:

`STEP or case → mesh → documented solver deck → dry-run or run → JSON summary`

Not a new solver and not a workbench. Requirement: https://github.com/linux-engineering-tools/community/issues/7

If your project already exposes this as a stable CLI, a pointer is enough.

## CalculiX

Title: `Machine-readable summary after a deck dry-run (max displacement / error)`

Ask whether `ccx` (or a documented wrapper) can validate a deck and emit a structured summary without a full GUI host.

## Elmer

Title: `CLI JSON summary for a documented Elmer case (dry-run)`

**Posted:** https://github.com/ElmerCSC/elmerfem/issues/885 — no reply yet.

## OpenFOAM

Title: `Stable dry-run of a case that reports mesh/dict errors with file:line`

(`foamRun -help` / `checkMesh` may already be the answer; we need a single documented contract.)

## Gmsh

Title: `STEP → .msh in batch with non-zero exit and a parseable error`

## FreeCAD FEM

Title: `Headless FEM pipeline (FreeCADCmd) that writes solver decks without the GUI`

If FreeCAD FEM will own the glue, LET will not incubate `let-solver-pipe`.

**Posted (with STEP/DXF):** https://github.com/FreeCAD/FreeCAD/discussions/32183

**Reply (ickby, 2026-08-27):** Mesh and solver setup cannot be done as command-line arguments on the FreeCAD executable. `FreeCADCmd` is a Python interpreter. Run `FreeCADCmd script.py`; the FEM workbench already exposes the needed API. LET treats that as the FreeCAD contract. A `let-solver-pipe` repo, if incubated, only calls that script (or CalculiX / Elmer / OpenFOAM directly).

## If they accept

RFC #22 stays upstream; contribute tests there.

## If they decline or the job is cross-solver glue they will not take

Maintainer may accept RFC #22. Thin wrapper only. Apache-2.0. Binary not named `let`.
