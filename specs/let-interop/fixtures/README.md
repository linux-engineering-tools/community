# Fixtures

Generate from public tools. Do not commit proprietary CAD.

Expect JSON must validate against [`../report.schema.json`](../report.schema.json) with `ok: true`.

| Id | File (generated) | Expect | How |
|---|---|---|---|
| `step-two-instances` | `step/two-instances.step` | `step/two-instances.json` | CadQuery or OCCT: two solid instances in one assembly, millimetres. Counts: `solids >= 1`, `instances == 2`. |
| `ifc-beam-column` | `ifc/beam-column.ifc` | `ifc/beam-column.json` | IfcOpenShell: one `IfcBeam`, one `IfcColumn`, one connection, one property set. |
| `dxf-rect` | `dxf/rect.dxf` | `dxf/rect.json` | LibreCAD or a documented DXF subset: one closed rectangle, length checks. |
| `ipc2581-two-layer` | `pcb/two-layer.xml` | `pcb/two-layer.json` | KiCad (or Horizon) export of a two-layer fixture board: layer count, net count, drill hits. |

Generation must be a documented command in the incubated repo (or in an upstream test tree if they take the suite). Community does not store vendor binaries.

Example expect (`step/two-instances.json`):

```json
{
  "ok": true,
  "fixture": "step-two-instances",
  "format": "step-ap242",
  "units": "millimetre",
  "counts": { "solids": 2, "instances": 2 },
  "tolerance": { "length": 1e-3, "count": 0 }
}
```
