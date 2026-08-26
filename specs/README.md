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

Drafts. **No org repo until RFC + maintainer decision + upstream asked.**

| Spec | Job | Requirement | RFC |
|---|---|---|---|
| [`omarchy-desktop/`](omarchy-desktop/) | Wayland / Omarchy GUI contract | #1 | — (not a tool) |
| [`geometry-harness/`](geometry-harness/) | OCCT/FreeCAD op reliability tests | #6 | — (upstream-first) |
| [`let-interop/`](let-interop/) | Open-format round-trip harness | #8, #14, #15 | #21 |
| [`let-solver-pipe/`](let-solver-pipe/) | CLI pre/post over existing solvers | #7 | #22 |
| [`instrument-map/`](instrument-map/) | Instrument identity → existing FOSS | #10 | — (catalog + thin CLI) |

