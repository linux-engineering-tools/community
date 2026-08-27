# Fixtures

| Id | Input | Expect | Job |
|---|---|---|---|
| `fea-cantilever` | `fea/cantilever.step` | `fea/cantilever.json` | Short cantilever solid; CalculiX or Elmer deck; `--dry-run` must succeed. Live solve may fill `max_displacement`. FreeCAD path is `FreeCADCmd fea/cantilever.py` (FEM Python API), not argv on the executable. |
| `cfd-lid-cavity` | `cfd/lid-cavity/` (OpenFOAM case tree, documented version) | `cfd/lid-cavity.json` | Lid-driven cavity; `--dry-run` validates dictionaries and mesh presence. |

Expect files validate against [`../summary.schema.json`](../summary.schema.json).

Example (`fea/cantilever.json`):

```json
{
  "ok": true,
  "solver": "calculix",
  "dry_run": true,
  "geom": "fea/cantilever.step"
}
```

Generate the STEP with CadQuery/OCCT. Use a documented OpenFOAM tutorial case as the CFD starting point (license-compatible, version-pinned in the incubated README). Do not vendor a full solver.
