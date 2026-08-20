# Linux Engineering Tools (LET)

Capability-first, clean-room, Linux-native engineering tools.

This repository is the **requirements board** and project home. Tools are incubated in other repositories under [linux-engineering-tools](https://github.com/linux-engineering-tools) only after a public spec exists and contributing upstream is the wrong home.

## What this is

Engineers who want to work on Linux still hit missing or weak tools in mechanical CAD, CAM, production drawings, PDM, and a long tail of desktop engineering software. PCB layout is largely served by existing FOSS. Solvers for FEA/CFD often already run on Linux; the gaps are elsewhere.

LET collects **jobs to be done**, written as capabilities and acceptance tests, then either:

1. Sends the work **upstream** to an existing project, or
2. **Incubates** a new tool under this organization.

## What this is not

- A clone of a named commercial product
- A place to paste proprietary source, UI layouts, leaked manuals, or NDA workflows
- A fork farm. Existing FOSS is listed in [`catalog/README.md`](catalog/README.md); contribute there first
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
| Fabrication (CAM, CNC, 3D print) | domain `cam` / `cnc` / `print` | [catalog/fabrication.md](catalog/fabrication.md) |
| Electronics (EDA, bench) | domain `eda` / `bench` | [catalog/electronics.md](catalog/electronics.md) |

## Desktop target

GUI tools must work as native Wayland apps on [Omarchy](https://omarchy.org/) (Hyprland). Super-key chords belong to the compositor. See [`agents/skills/omarchy-desktop/SKILL.md`](agents/skills/omarchy-desktop/SKILL.md).

## License

Apache License 2.0. Contributions are under the Developer Certificate of Origin (DCO). See [`CONTRIBUTING.md`](CONTRIBUTING.md).
