# Spaces

How LET is partitioned. One organization, one requirements repo, several **spaces**. Do not create a repo per topic until a space has its own maintainers and sustained traffic.

## Why spaces

3D CAD, mesh modelling, 3D printing, CNC, EDA, and bench instruments are different jobs and different people. One undifferentiated issue list buries all of them. One repo per topic at this stage creates empty rooms and duplicated process.

| Layer | What it is | What it is not |
|---|---|---|
| **Org** | `linux-engineering-tools` | A second GitHub org per topic |
| **Repo** | `community` for requirements, RFCs, catalog, skills | A CAD repo, a print repo, … until incubation |
| **Space** | Discussion category + project view | A political or identity grouping |
| **Domain** | Fine-grained issue label (`cad`, `print`, `bench`, …) | A new tracker |
| **Incubated tool** | Its own org repo after a spec | A place to file unrelated requirements |

## Spaces and domains

| Space | Domains | Typical jobs |
|---|---|---|
| **Mechanical** | `cad`, `mesh`, `drawings` | Parametric solids, mesh/organic models, manufacturing drawings |
| **Fabrication** | `cam`, `cnc`, `print` | Toolpaths, CNC control, 3D-print slice/host |
| **Electronics** | `eda`, `bench` | Schematic/PCB, instruments, USB/JTAG repair |
| **Simulation** | `fea`, `cfd` | Solvers and pre/post |
| **Data** | `pdm`, `interop` | Revisions, BOM, open-format round-trip |
| **Desktop** | `desktop` | Omarchy / Wayland contract (cross-cutting) |
| **Other** | `scientific`, `civil`, `other` | Process, automation, biomedical, nuclear until a space earns its own row |

`cad` is parametric engineering CAD. `mesh` is polygon/sculpt/subdivision modelling (the Blender-class job). They are not the same requirement. `cam` is toolpath generation; `cnc` is talking to the machine (LinuxCNC-class). `print` is slice, host, and printer firmware on Linux.

Catalog pages: [`catalog/README.md`](catalog/README.md). Fan-out plan: [`ROADMAP.md`](ROADMAP.md).

## Discussions vs issues

| Use | Where |
|---|---|
| “Does FOSS X exist? How do I run it?” | Discussions, **in that space’s category** |
| A job with standards and tests | Requirement **issue** (form), domain label set |
| Incubate a repo / change process | RFC **issue** |
| Off-topic | Close |

Issues stay on the form. Discussions are the healthy talk. Do not debate catalog trivia on a requirement issue.

### Categories to create in GitHub (UI)

The API cannot add discussion categories. In the `community` repo: **Settings → General → Discussions** (or the Discussions “edit categories” control), add:

| Category | Format | Purpose |
|---|---|---|
| Mechanical | Open-ended | CAD, mesh, drawings |
| Fabrication | Open-ended | CAM, CNC, 3D print |
| Electronics | Open-ended | EDA, bench, repair |
| Simulation | Open-ended | FEA, CFD |
| Data | Open-ended | PDM, interop |
| Desktop | Open-ended | Omarchy / Wayland |
| Q&A | Q&A | Keep the default; use when the space is unclear |
| Announcements | Announcements | Keep |

Disable or ignore **Polls** / **Ideas** / **Show and tell** if they become noise. **General** can stay as overflow.

After they exist, discussion links are:

`https://github.com/linux-engineering-tools/community/discussions/new?category=<slug>`

## Projects

Keep **one** org project: [Requirements](https://github.com/orgs/linux-engineering-tools/projects/1).

- Table **Triage** — everything
- Board **By stage** — group this view by the **Stage** field, not GitHub’s Status
- Board **By domain** — fine grain
- Filtered table views per space when the list is long (filter on Domain)

**Status** (Todo / In Progress / Done) means a human is implementing that item. Seeded requirements stay **Todo**. Pipeline state is **Stage** (`needs-triage`, `needs-spec`, `upstream-first`, `incubating`, `graduated`, `wont`). `upstream-first` is not In Progress.

**Split a space into its own GitHub Project** only when that space has a named maintainer and the main board is unusable without the filter. Auto-add by `domain:*` labels. Do not split the issue tracker.

## When a space gets its own repo

An RFC plus maintainer decision, and **all** of:

1. A person who will triage that space
2. Repeated requirements that are not just catalog questions
3. Either an incubated tool or a catalog/test-harness that does not belong in `community`

Until then: labels + discussions + project views.

## Routing

Maintainers (and agents) set `domain:` from the form. Space is implied by the table above. If a thread spans spaces (CAD → print), keep **one** requirement per job; link the other. Do not file “make a CAD-to-printer suite” as a single clone-spec.
