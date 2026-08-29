# Process / chemical free and open-source software (FOSS) on Linux

Steady-state thermo, kinetics, and plant-oriented simulation. Contribute **upstream**. Columns: [`README.md`](README.md). Terms: [`../TERMS.md`](../TERMS.md).

Plant-wide **layout CAD** and many unit-operation GUIs are still gaps; describe those jobs with DEXPI / ISO 15926 / CAPE-OPEN, not vendor flowsheet clones.

| Project | Job | Forge | Display |
|---|---|---|---|
| [DWSIM](https://dwsim.org/) | Process simulation | [GitHub](https://github.com/DanWBR/dwsim) | `unverified` |
| [COCO Simulator](https://www.cocosimulator.org/) | CAPE-OPEN flowsheeting | [site source](https://www.cocosimulator.org/) | `unverified` |
| [Cantera](https://cantera.org/) | Chemical kinetics / thermodynamics | [GitHub](https://github.com/Cantera/cantera) | `cli` |
| [OpenFOAM Foundation](https://openfoam.org/) | Reacting / process CFD | [GitHub](https://github.com/OpenFOAM/OpenFOAM-dev) | `cli` |
| [OpenFOAM (OpenCFD)](https://www.openfoam.com/) | Reacting / process CFD | [GitLab](https://gitlab.com/openfoam/core/openfoam) | `cli` |

GUI vs TUI: Cantera and OpenFOAM are library/TUI. DWSIM has a GUI; prefer its documented file formats for LET tests. COCO publishes source from its site; it is historically Windows-first. Confirm a Linux path before treating it as head-start GUI.
