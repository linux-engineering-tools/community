# Spec draft: `let-interop`

Open-format **round-trip test suite**. Not a CAD. Not a clone of a commercial translator.

**Status:** draft — needs requirement #8 plus this spec accepted, then RFC before any repo.

## Job

An engineer (or CI) on Linux proves that a given tool chain can import and export published geometry/electronics formats without silent data loss.

## Standards

- STEP AP242 (ISO 10303-242) assemblies
- IFC (ISO 16739) for building/structural
- DXF (published Autodesk spec) 2D
- IPC-2581 (PCB manufacturing) where applicable

Vendor binaries (`.rvt`, `.pln`, `.adb`, `.nxasm`) are **out of scope**.

## CLI (proposed)

`let-interop` is a working name only. Final binary must not be `let`.

```
let-interop check --in fixture.step --expect fixture.json
let-interop roundtrip --in fixture.step --out /tmp/out.step --report report.json
```

Exit 0 on pass; non-zero on missing entities, unit mismatch, or failed schema validate. JSON report lists counts (solids, instances, properties).

## Acceptance tests

- In-tree fixtures for STEP AP242 (assembly with two instances) and IFC (one IfcBeam + IfcColumn).
- Round-trip: entity counts and bounding box within documented tolerance.
- Failures name the standard clause or schema path.

## Upstream check

OpenCASCADE, IfcOpenShell, FreeCAD, KiCad already parse these formats. This tool is a **harness** if those projects will not host a shared, discipline-neutral fixture suite. Ask them first (`catalog/` pages). Do not reimplement kernels.

## GUI

None. Library + CLI.

## License

Apache-2.0 if incubated.
