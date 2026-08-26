# Spec: `let-interop`

Open-format **round-trip test suite**. Not a CAD. Not a clone of a commercial translator.

**Status:** draft — requirements [#8](https://github.com/linux-engineering-tools/community/issues/8), [#14](https://github.com/linux-engineering-tools/community/issues/14), [#15](https://github.com/linux-engineering-tools/community/issues/15). RFC [#21](https://github.com/linux-engineering-tools/community/issues/21). **Do not create a repo** until upstream is asked and a maintainer accepts the RFC.

## Job

An engineer (or CI) on Linux proves that a given tool chain can import and export published geometry and electronics formats without silent data loss.

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
```

`--dry-run` parses input, validates against the expect file, and writes the report **without** calling an external host export. Exit 0 if parse + counts match.

### Exit codes

| Code | Meaning |
|---|---|
| 0 | Pass |
| 2 | Input missing, unreadable, or schema-invalid |
| 3 | Round-trip drift beyond tolerance (counts, bbox, units) |
| 4 | Host/kernel subprocess failed (named in `error`) |
| 64 | Usage (`--help` is 0) |

## JSON report

Schema: [`report.schema.json`](report.schema.json). Required fields: `ok`, `fixture`, `format`, `counts`, `units`. On failure, `error` names the standard path (STEP entity, IFC class+GlobalId, DXF entity type, IPC-2581 XPath).

## Fixtures

Named in [`fixtures/README.md`](fixtures/README.md). Generate from public tools (CadQuery, IfcOpenShell, KiCad). Do not check in proprietary CAD.

## Acceptance tests

- `check` on each fixture exits 0 and matches the expect JSON.
- `roundtrip` on STEP and IFC: entity counts and bounding box within the expect file’s `tolerance`.
- `roundtrip --dry-run` never invokes FreeCAD/KiCad/IfcConvert.
- Failures print JSON on stdout or `--report`; non-zero exit.
- Suite is headless (no GUI).

## Upstream check

OpenCASCADE, IfcOpenShell, FreeCAD, and KiCad already parse these formats. This tool is a **harness** only if they will not host a shared, discipline-neutral fixture suite.

Copy-paste asks: [`upstream-ask.md`](upstream-ask.md). Record the issue/forum URL on RFC #21 before any `status:incubating`.

## GUI

None. Library + CLI.

## License

Apache-2.0 if incubated.
