# Scientific, biomedical, and nuclear free and open-source software (FOSS) on Linux

Research-grade tools. **Regulatory deeming** (medical device, nuclear licensing) is a process gap, not a missing solver. Do not incubate a certified replacement for a licensed code. Columns: [`README.md`](README.md). Terms: [`../TERMS.md`](../TERMS.md).

## Biomedical imaging

| Project | Job | Forge | Display |
|---|---|---|---|
| [DCMTK](https://dcmtk.org/) | DICOM toolkit | [GitHub (official mirror)](https://github.com/DCMTK/dcmtk) | `cli` |
| [Orthanc](https://www.orthanc-server.com/) | DICOM server | [Mercurial](https://orthanc.uclouvain.be/hg/orthanc/) | `web` |
| [PyDICOM](https://pydicom.github.io/) | DICOM in Python | [GitHub](https://github.com/pydicom/pydicom) | `cli` |
| [FSL](https://fsl.fmrib.ox.ac.uk/) | Neuroimaging analysis | [FMRIB GitLab](https://git.fmrib.ox.ac.uk/fsl) | `unverified` |

Standards: DICOM PS3. Jobs are extract / convert / summarize, not vendor PACS GUIs.

## Radiation / nuclear (research)

| Project | Job | Forge | Display |
|---|---|---|---|
| [OpenMC](https://docs.openmc.org/) | Monte Carlo particle transport | [GitHub](https://github.com/openmc-dev/openmc) | `cli` |
| [Geant4](https://geant4.web.cern.ch/) | Particle transport toolkit | [CERN GitLab](https://gitlab.cern.ch/geant4/geant4) | `cli` |

MCNP-class **licensed** codes are out of scope. Open interchange of mesh/tallies (HDF5, VTK) is in scope.

## Numerical

See the scientific-computing table in [`README.md`](README.md) (Octave, SciPy, Julia, PETSc, Trilinos).
