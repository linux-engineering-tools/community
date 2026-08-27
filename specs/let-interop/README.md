# Spec: `let-interop`

Open-format test suite: round-trip for STEP / DXF / IPC-2581; parse and IfcDiff for IFC. Not computer-aided design (CAD). Not a clone of a commercial translator. Terms: [`../../TERMS.md`](../../TERMS.md).

**Status:** incubating — [linux-engineering-tools/let-interop](https://github.com/linux-engineering-tools/let-interop). Requirements [#8](https://github.com/linux-engineering-tools/community/issues/8), [#14](https://github.com/linux-engineering-tools/community/issues/14), [#15](https://github.com/linux-engineering-tools/community/issues/15). RFC [#21](https://github.com/linux-engineering-tools/community/issues/21). Docs-first: CLI contract and `--dry-run` stub. Kernels stay upstream.

## Job

An engineer (or CI) on Linux proves that a given tool chain can handle published geometry and electronics formats without silent data loss.

- **STEP / DXF / IPC-2581:** write the file out, read it back, compare counts, units, and bounds (true round-trip through a kernel or host).
- **IFC:** parse with IfcOpenShell. Compare two IFC files with [IfcDiff](https://docs.ifcopenshell.org/ifcdiff.html) (geometry, properties, type / container / aggregate relationships). IfcOpenShell has no non-IFC native model, so it does not import/export through a separate CAD kernel. Geometry rewrite, if needed, is [Bonsai](https://bonsaibim.org/), not this harness.

## Standards

- STEP AP242 (ISO 10303-242) assemblies; AP214 as a documented fallback
- IFC (ISO 16739); prefer IFC4 / IFC4.3
- DXF (published Autodesk spec) 2D subset
- IPC-2581 (PCB manufacturing) where the host already writes it

Vendor binaries (`.rvt`, `.pln`, `.adb`, `.nxasm`) are **out of scope**.

## CLI (proposed)

Working name only. Final binary must not be `let`.

```
let-interop --help
let-interop check --in fixtures/step/two-instances.step --expect fixtures/step/two-instances.json
let-interop roundtrip --in fixtures/step/two-instances.step --out /tmp/out.step --report report.json
let-interop roundtrip --dry-run --in fixtures/step/two-instances.step --report report.json
let-interop diff --old fixtures/ifc/beam-column.ifc --new /tmp/out.ifc --report report.json
```

`--dry-run` parses input, validates against the expect file, and writes the report **without** calling an external host export. Exit 0 if parse + counts match.

`diff` is the IFC path: wrap `python -m ifcdiff` (or the IfcDiff library). Do not treat entity counts as the IFC comparison.

### Exit codes

| Code | Meaning |
|---|---|
| 0 | Pass |
| 2 | Input missing, unreadable, or schema-invalid |
| 3 | Drift beyond tolerance (STEP/DXF counts and bbox, or a non-empty IfcDiff change register) |
| 4 | Host/kernel subprocess failed (named in `error`) |
| 64 | Usage (`--help` is 0) |

## JSON report

Schema: [`report.schema.json`](report.schema.json). Required fields: `ok`, `fixture`, `format`, `counts`, `units`. On failure, `error` names the standard path (STEP entity, IFC class+GlobalId, DXF entity type, IPC-2581 XPath).

## Fixtures

Named in [`fixtures/README.md`](fixtures/README.md). Generate from public tools (CadQuery, IfcOpenShell, KiCad). Do not check in proprietary CAD.

## Acceptance tests

- `check` on each fixture exits 0 and matches the expect JSON.
- `roundtrip` on STEP: entity counts and bounding box within the expect file's `tolerance`.
- IFC `diff` of the fixture against itself: empty added / deleted / changed lists.
- IFC `diff` against a mutant that drops the beam-column connection or a property set: IfcDiff reports that relationship or property change (counts-only must not pass).
- IFC `diff` against a mutant that keeps entity counts but changes a placement: IfcDiff reports the geometry or attribute change.
- `roundtrip --dry-run` never invokes FreeCAD, KiCad, IfcConvert, or IfcDiff.
- Failures print JSON on stdout or `--report`; non-zero exit. IFC `error.path` is `Class:GlobalId` from IfcDiff.
- Suite is headless (no GUI, no Bonsai).

## Upstream check

OpenCASCADE, IfcOpenShell, FreeCAD, and KiCad already parse these formats. This tool is a **harness** that calls them. Recorded asks and replies: [`upstream-ask.md`](upstream-ask.md).

## GUI

None. Library + CLI.

## License

Apache-2.0 if incubated.
