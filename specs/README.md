# Specs

Public specifications for work that might become a LET tool. Nothing is implemented from a proprietary original.

A spec is required **before** incubating a repo (`agents/skills/incubate-tool/SKILL.md`).

Each spec lives in `specs/<short-name>/` and states:

- Job to be done
- Published standards and file formats
- CLI (commands, exit codes, fixtures)
- Acceptance tests
- Upstream check (why not an existing project)
- Desktop contract, if there is a GUI

Start from an accepted requirement issue. Do not put clone-specs here.

Drafts from the Omarchy research extracts:

- [`let-interop/`](let-interop/) — open-format round-trip harness (STEP, IFC, DXF, IPC-2581)
- [`let-solver-pipe/`](let-solver-pipe/) — CLI pre/post over existing FEA/CFD solvers

