# Data / PDM FOSS on Linux

Parts, stock, BOM, revisions, and open-format interchange. Contribute **upstream** before incubating. See [`SPACES.md`](../SPACES.md).

`pdm` is revisioned CAD/BOM/change records. `interop` is proving open formats round-trip (STEP, IFC, DXF, IPC-2581). They are not a vendor PDM clone.

## Parts / stock / BOM (`domain:pdm`)

| Project | Job |
|---|---|
| [InvenTree](https://inventree.org/) | Parts, stock, BOM, suppliers |
| [Cascadia PLM](https://cascadiaplm.com/) | Self-hosted PLM, BOM, change records |
| [Part-DB](https://docs.part-db.de/) | Electronic-parts inventory |

Git plus open files (STEP, KiCad, FreeCAD) is a valid small-team revision path. Do not incubate a PDM because a shop still uses folders.

## Interop (`domain:interop`)

Kernels and hosts that already parse published formats. A LET harness, if incubated, only **reports** round-trip drift; it does not reimplement them.

| Project | Job |
|---|---|
| [Open CASCADE Technology](https://dev.opencascade.org/) | STEP and other CAD exchange (kernel) |
| [IfcOpenShell](https://ifcopenshell.org/) | IFC (ISO 16739) parse / geometry |
| [FreeCAD](https://www.freecad.org/) | STEP / DXF import-export in a CAD host |
| [KiCad](https://www.kicad.org/) | Gerber / IPC-2581 board interchange |

See [`../specs/let-interop/`](../specs/let-interop/) and requirements #5, #8, #14, #15.
