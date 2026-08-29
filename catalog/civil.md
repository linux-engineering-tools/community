# Civil / structural / geospatial free and open-source software (FOSS) on Linux

Contribute **upstream** before incubating. `domain:civil` plus interoperability (`interop`) for open building information modelling (BIM). Columns: [`README.md`](README.md). Terms: [`../TERMS.md`](../TERMS.md).

Native Linux **does not** currently provide lossless edit of vendor BIM binaries. The professional bar here is **IFC** (ISO 16739) and open GIS, not `.rvt` / `.pln` editability.

## BIM / structural (`domain:civil`)

| Project | Job | Forge | Display |
|---|---|---|---|
| [IfcOpenShell](https://ifcopenshell.org/) | IFC parse, geometry, Python API. Comparison: [IfcDiff](https://docs.ifcopenshell.org/ifcdiff.html). No non-IFC native model. | [GitHub](https://github.com/IfcOpenShell/IfcOpenShell) | `cli` |
| [Bonsai](https://bonsaibim.org/) (Blender) | IFC authoring in Blender, including geometric representation rewrite | [GitHub](https://github.com/IfcOpenShell/IfcOpenShell) | `both` |
| [FreeCAD](https://www.freecad.org/) Arch / BIM | Architectural / BIM solids | [GitHub](https://github.com/FreeCAD/FreeCAD) | `both` |
| [Code_Aster](https://code-aster.org/) | Structural analysis | [GitLab](https://gitlab.com/codeaster/src) | `cli` |
| [SALOME](https://www.salome-platform.org/) | CAD / mesh / pre-post (Code_Aster stack) | [GitHub](https://github.com/SalomePlatform) | `unverified` |
| [FRAME3DD](https://frame3dd.sourceforge.net/) | Frame analysis | [SourceForge](https://sourceforge.net/projects/frame3dd/) | `cli` |

SALOME details: [`simulation.md`](simulation.md). Blender display: [`desktop.md`](desktop.md).

## Geospatial (`domain:civil` / environment)

| Project | Job | Forge | Display |
|---|---|---|---|
| [QGIS](https://qgis.org/) | Desktop GIS | [GitHub](https://github.com/qgis/QGIS) | `unverified` |
| [PDAL](https://pdal.io/) | Point-cloud pipelines | [GitHub](https://github.com/PDAL/PDAL) | `cli` |
| [GDAL](https://gdal.org/) | Raster/vector interchange | [GitHub](https://github.com/OSGeo/gdal) | `cli` |

LibreCAD/QCAD are 2D CAD (`catalog/mechanical.md`); they are not BIM authoring.
