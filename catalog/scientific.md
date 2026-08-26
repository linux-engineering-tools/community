# Scientific, biomedical, and nuclear free and open-source software (FOSS) on Linux

Research-grade tools. **Regulatory deeming** (medical device, nuclear licensing) is a process gap, not a missing solver. Do not incubate a certified replacement for a licensed code. Terms: [`../TERMS.md`](../TERMS.md).

## Biomedical imaging

| Project | Job |
|---|---|
| [DCMTK](https://dcmtk.org/) | DICOM toolkit |
| [Orthanc](https://www.orthanc-server.com/) | DICOM server |
| [PyDICOM](https://pydicom.github.io/) | DICOM in Python |
| [FSL](https://fsl.fmrib.ox.ac.uk/) | Neuroimaging analysis |

Standards: DICOM PS3. Jobs are extract / convert / summarize, not vendor PACS GUIs.

## Radiation / nuclear (research)

| Project | Job |
|---|---|
| [OpenMC](https://docs.openmc.org/) | Monte Carlo particle transport |
| [Geant4](https://geant4.web.cern.ch/) | Particle transport toolkit |

MCNP-class **licensed** codes are out of scope. Open interchange of mesh/tallies (HDF5, VTK) is in scope.

## Numerical

See the scientific-computing table in [`README.md`](README.md) (Octave, SciPy, Julia, PETSc, Trilinos).
