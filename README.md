# Linux Engineering Tools (LET)

Capability-first, clean-room, Linux-native engineering tools.

This repository is the **requirements board** and project home. Tools are incubated in other repositories under [linux-engineering-tools](https://github.com/linux-engineering-tools) only after a public specification exists and contributing **upstream** (to an existing project) is the wrong home.

Acronyms and domain words: [`TERMS.md`](TERMS.md). Spell the expanded form on first use in a document, then the short form.

## What this is

Engineers who want to work on Linux still hit missing or weak tools in mechanical computer-aided design (CAD), computer-aided manufacturing (CAM), production drawings, product data management (PDM), and a long tail of desktop engineering software. Printed circuit board (PCB) layout is largely served by existing free and open-source software (FOSS). Solvers for finite element analysis (FEA) and computational fluid dynamics (CFD) often already run on Linux; the gaps are elsewhere.

LET collects **jobs to be done**, written as capabilities and acceptance tests, then either:

1. Sends the work **upstream** to an existing project, or
2. **Incubates** a new tool under this organization.

## What this is not

- A clone of a named commercial product
- A place to paste proprietary source, UI layouts, leaked manuals, or NDA workflows
- A fork farm. Existing FOSS is listed in [`catalog/README.md`](catalog/README.md) (homepage, canonical forge, X11/Wayland note); contribute there first
- A political project. Docs cover conduct, process, and engineering. Nothing else

## How to participate

1. Read [`CONTRIBUTING.md`](CONTRIBUTING.md) before opening an issue.
2. File a **requirement** with the [issue form](https://github.com/linux-engineering-tools/community/issues/new/choose). Describe the job, inputs/outputs, standards, and tests — not a product to copy.
3. If you are using an agent, point it at [`AGENTS.md`](AGENTS.md).

Open requirements: [Issues](https://github.com/linux-engineering-tools/community/issues) · [Project board](https://github.com/orgs/linux-engineering-tools/projects/1). Blank issues are disabled; use the form.

Talk in [Discussions](https://github.com/linux-engineering-tools/community/discussions), in the category for that [space](SPACES.md) (Mechanical, Fabrication, Electronics, …). Spaces are labels and discussion rooms, not extra GitHub organizations.

| Space | File a requirement | Catalog |
|---|---|---|
| Mechanical (CAD, mesh, drawings) | domain `cad` / `mesh` / `drawings` | [catalog/mechanical.md](catalog/mechanical.md) |
| Fabrication (CAM, computer numerical control (CNC), 3D print) | domain `cam` / `cnc` / `print` | [catalog/fabrication.md](catalog/fabrication.md) |
| Electronics (electronic design automation (EDA), bench) | domain `eda` / `bench` | [catalog/electronics.md](catalog/electronics.md) |
| Simulation (FEA, CFD) | domain `fea` / `cfd` | [catalog/simulation.md](catalog/simulation.md) |
| Data (PDM, interoperability) | domain `pdm` / `interop` | [catalog/data.md](catalog/data.md) |
| Civil / geographic information systems (GIS) / building information modelling (BIM) | domain `civil` | [catalog/civil.md](catalog/civil.md) |
| Process / chemical | domain `process` | [catalog/process.md](catalog/process.md) |
| Automation / control | domain `automation` | [catalog/automation.md](catalog/automation.md) |
| Scientific / biomedical | domain `scientific` | [catalog/scientific.md](catalog/scientific.md) |
| Desktop (Wayland) | domain `desktop` | [catalog/desktop.md](catalog/desktop.md) |

Research-backed fan-out (head-start vs upstream vs possible incubation): [`ROADMAP.md`](ROADMAP.md).

## Desktop target

Graphical user interface (GUI) tools must work as native [Wayland](https://wayland.freedesktop.org/) apps. [Omarchy](https://omarchy.org/) (Hyprland) is a test desktop. Shortcuts live in a simple user config file, the same idea as Omarchy's bindings file, so users can avoid conflicts with their operating system. Defaults use Ctrl / Shift / Alt. See [`agents/skills/omarchy-desktop/SKILL.md`](agents/skills/omarchy-desktop/SKILL.md).

## License

Apache License 2.0. Contributions are under the Developer Certificate of Origin (DCO). See [`CONTRIBUTING.md`](CONTRIBUTING.md).
