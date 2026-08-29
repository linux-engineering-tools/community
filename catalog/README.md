# Existing free and open-source software (FOSS)

Linux Engineering Tools (LET) does not replace these. File a requirement only if the job is still unmet after the catalog for that **space**. Prefer patches **upstream** (the existing project). Use the **Forge** URL when you file there, not a GitHub mirror. Terms: [`../TERMS.md`](../TERMS.md).

Maps, not rankings. Layout follows [`SPACES.md`](../SPACES.md). This catalog is FOSS. Named commercial products stay out except as one-line motivation on a requirement.

| Space | Catalog |
|---|---|
| Mechanical (computer-aided design (`cad`), mesh, drawings) | [`mechanical.md`](mechanical.md) |
| Fabrication (computer-aided manufacturing (`cam`), computer numerical control (`cnc`), print) | [`fabrication.md`](fabrication.md) |
| Electronics (electronic design automation (`eda`), bench) | [`electronics.md`](electronics.md) |
| Simulation (finite element analysis (`fea`), computational fluid dynamics (`cfd`)) | [`simulation.md`](simulation.md) |
| Data (product data management (`pdm`), interoperability (`interop`)) | [`data.md`](data.md) |
| Desktop (`desktop`) | [`desktop.md`](desktop.md) |
| Civil / geospatial (`civil`) | [`civil.md`](civil.md) |
| Process / chemical (`process`) | [`process.md`](process.md) |
| Automation / control (`automation`) | [`automation.md`](automation.md) |
| Scientific / biomedical / nuclear (`scientific`) | [`scientific.md`](scientific.md) |

Research extracts and the fan-out plan: [`../ROADMAP.md`](../ROADMAP.md).

## Columns

Space pages use **Project | Job | Forge | Display**.

- **Project** is the homepage.
- **Forge** is the canonical source repository (where to send patches). GitHub mirrors of GitLab or Savannah projects are not upstream.
- **Display** is how the Linux graphical user interface (GUI) talks to the session, when there is one. Tokens:

| Token | Meaning |
|---|---|
| `cli` | Library, solver, firmware, kernel module, or command-line only |
| `web` | Browser user interface |
| `x11` | Upstream treats X11 as the supported Linux path |
| `xwayland` | Runs on Wayland compositors only as an X11 client |
| `wayland` | Native Wayland is a supported Linux path |
| `both` | Native X11 and native Wayland |
| `unverified` | There is a GUI; we have no cited public statement |

Display is a literature note, not an Omarchy test. Do not claim Omarchy verification unless it was run on that stack. Citations for GUIs live in [`desktop.md`](desktop.md). LET-incubated GUIs still follow [`../agents/skills/omarchy-desktop/SKILL.md`](../agents/skills/omarchy-desktop/SKILL.md): native Wayland is required; `x11` or `xwayland` as the only path is a defect.

## Where to scan

Re-check these when expanding the catalog. Do not treat `gitlab.com/explore/projects/topics/CAD` as a tool list (it is mostly models and web apps).

| Source | Why |
|---|---|
| [GitLab.com groups](https://gitlab.com/explore/groups) | KiCad, OpenFOAM (OpenCFD), Code_Aster, PETSc, IgH EtherCAT |
| [Kitware GitLab](https://gitlab.kitware.com) | Visualization Toolkit (VTK), ParaView |
| [ONELAB GitLab](https://gitlab.onelab.info) | Gmsh and related mesh/FEM tools |
| [CERN GitLab](https://gitlab.cern.ch) | Geant4 |
| [SourceForge](https://sourceforge.net/directory/cad/) | Still canonical for several EDA/CAM rows |
| [GNU Savannah](https://savannah.gnu.org) | GNU Octave, LibreDWG |
| GitHub | Default for many CAD/CAM/EDA projects |
| [Blender Gitea](https://projects.blender.org) | Blender |
| Distro indexes (Arch, Debian [Salsa](https://salsa.debian.org), Fedora) | Existence check, not upstream |
| [Codeberg](https://codeberg.org), [sourcehut](https://sourcehut.org) | Occasional CAD/CAM; confirm they are not mirrors |

Also useful: [invent.kde.org](https://invent.kde.org) and [gitlab.gnome.org](https://gitlab.gnome.org) for toolkit bugs, not as a CAD catalog.

## Scientific computing

| Project | Job | Forge | Display |
|---|---|---|---|
| [GNU Octave](https://octave.org/) | Numerical computing | [Savannah (hg)](https://hg.savannah.gnu.org/hgweb/octave) | `cli` |
| [NumPy](https://numpy.org/) / [SciPy](https://scipy.org/) | Numerical computing in Python | [NumPy](https://github.com/numpy/numpy), [SciPy](https://github.com/scipy/scipy) | `cli` |
| [Julia](https://julialang.org/) | Numerical / scientific computing | [GitHub](https://github.com/JuliaLang/julia) | `cli` |
| [PETSc](https://petsc.org/) | Sparse / nonlinear solvers | [GitLab](https://gitlab.com/petsc/petsc) | `cli` |
| [Trilinos](https://trilinos.github.io/) | HPC solver stack | [GitHub](https://github.com/trilinos/Trilinos) | `cli` |

If you add a project, put it on the space page with Forge and Display, and link the upstream contribution guide from the LET issue.
