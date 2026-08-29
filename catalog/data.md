# Data / product data management (PDM) free and open-source software (FOSS) on Linux

Parts, stock, bill of materials (BOM), revisions, and open-format interchange. Contribute **upstream** before incubating. See [`SPACES.md`](../SPACES.md). Columns: [`README.md`](README.md). Terms: [`../TERMS.md`](../TERMS.md).

`pdm` is revisioned CAD/BOM/change records. `interop` is proving open formats round-trip (STEP, IFC, DXF, IPC-2581). They are not a vendor PDM clone.

## Parts / stock / BOM (`domain:pdm`)

| Project | Job | Forge | Display |
|---|---|---|---|
| [InvenTree](https://inventree.org/) | Parts, stock, BOM, suppliers | [GitHub](https://github.com/inventree/InvenTree) | `web` |
| [Cascadia PLM](https://cascadiaplm.com/) | Self-hosted PLM, BOM, change records (open-core AGPL) | [GitHub](https://github.com/Cascadia-PLM/Cascadia-App) | `web` |
| [Part-DB](https://docs.part-db.de/) | Electronic-parts inventory | [GitHub](https://github.com/Part-DB/Part-DB-server) | `web` |

Git plus open files (STEP, KiCad, FreeCAD) is a valid small-team revision path. Do not incubate a PDM because a shop still uses folders.

## Interop (`domain:interop`)

Kernels and hosts that already parse published formats. A LET harness, if incubated, only **reports** round-trip drift; it does not reimplement them.

| Project | Job | Forge | Display |
|---|---|---|---|
| [Open CASCADE Technology](https://dev.opencascade.org/) | STEP and other CAD exchange (kernel) | [GitHub](https://github.com/Open-Cascade-SAS/OCCT) | `cli` |
| [LibreDWG](https://www.gnu.org/software/libredwg/) | DWG read/write (GNU; not a CAD) | [Savannah](https://savannah.gnu.org/projects/libredwg) | `cli` |
| [IfcOpenShell](https://ifcopenshell.org/) | IFC (ISO 16739) parse / geometry | [GitHub](https://github.com/IfcOpenShell/IfcOpenShell) | `cli` |
| [FreeCAD](https://www.freecad.org/) | STEP / DXF import-export in a CAD host | [GitHub](https://github.com/FreeCAD/FreeCAD) | `both` |
| [KiCad](https://www.kicad.org/) | Gerber / IPC-2581 board interchange | [GitLab](https://gitlab.com/kicad/code/kicad) | `x11` |

See [`../specs/let-interop/`](../specs/let-interop/) and requirements #5, #8, #14, #15.
