# Specs

Public specifications for work that might become a Linux Engineering Tools (LET) tool. Nothing is implemented from a proprietary original. Terms: [`../TERMS.md`](../TERMS.md).

A spec is required **before** incubating a repo (`agents/skills/incubate-tool/SKILL.md`).

Each spec lives in `specs/<short-name>/` and states:

- Job to be done
- Published standards and file formats
- Command-line interface (CLI): commands, exit codes, fixtures
- Acceptance tests
- Upstream check (why not an existing project)
- Desktop contract, if there is a graphical user interface (GUI)

Start from an accepted requirement issue. Do not put clone-specs here.

Drafts. **No org repo until RFC + maintainer decision.** `let-interop` is past that gate.

| Spec | Job | Requirement | RFC |
|---|---|---|---|
| [`omarchy-desktop/`](omarchy-desktop/) | Wayland / Omarchy GUI contract | #1 | — (not a tool) |
| [`geometry-harness/`](geometry-harness/) | Open CASCADE Technology (OCCT) / FreeCAD operation reliability tests | #6 | — (upstream-first) |
| [`let-interop/`](let-interop/) | Open-format round-trip harness ([repo](https://github.com/linux-engineering-tools/let-interop)) | #8, #14, #15 | #21 (incubating) |
| [`let-solver-pipe/`](let-solver-pipe/) | CLI prepare/inspect pipeline over existing solvers | #7 | #22 |
| [`instrument-map/`](instrument-map/) | Instrument identity → existing free and open-source software | #10 | — (catalog + thin CLI) |

