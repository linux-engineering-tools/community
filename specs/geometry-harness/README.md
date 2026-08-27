# Spec draft: geometry-operation reliability harness

Requirement [#6](https://github.com/linux-engineering-tools/community/issues/6). **Upstream-first:** Open CASCADE Technology and FreeCAD. This is not a geometry kernel. Do not incubate a boundary-representation (B-rep) replacement. Terms: [`../../TERMS.md`](../../TERMS.md).

**Status:** draft — public test contract so LET can contribute fixtures upstream.

## Job

Parametric Boolean, fillet, shell, and similar solid operations on production-sized models complete or fail with a **stable, reported** error — not a silent corrupt body or a crash. Interactive view of large triangulations should remain usable (that part is the CAD host).

## Standards

- Geometry kernel already in FOSS (OCCT)
- Exchange: STEP AP242
- Report: JSON (schema below)

## CLI (proposed host)

Prefer `DRAWEXE` (OCCT) and/or `FreeCADCmd`. A LET binary only if they will not take the suite.

```
geometry-harness run --op boolean --in fixture.step --json report.json
geometry-harness run --op fillet --in fixture.step --json report.json
geometry-harness run --dry-run --in fixture.step
```

`--dry-run` loads the STEP and lists planned ops; no mutation.

### Exit codes

| Code | Meaning |
|---|---|
| 0 | Operation succeeded; JSON `ok: true` |
| 2 | Input invalid |
| 3 | Operation failed with a structured error (not a crash) — still JSON |
| 4 | Crash / timeout / silent corrupt body |
| 64 | Usage |

Exit 3 is a **pass of the harness** if the kernel reports a structured error. Exit 4 is a harness failure.

## JSON report (minimum)

```json
{
  "ok": true,
  "op": "boolean",
  "fixture": "box-cylinder.step",
  "elapsed_ms": 120,
  "deterministic": true,
  "error": null
}
```

On failure: `ok: false`, `error.code`, `error.message` (no proprietary kernel dumps required).

## Fixtures

Public STEP only. Start small (box ∪/∩/– cylinder, fillet on a box edge, shell of a solid). Production-sized models later, still open formats.

Repeat rebuild N times (document N, start with 3) must be deterministic: same `ok` and same solid count.

## Acceptance tests

- Listed ops on each fixture: success **or** structured error; no crash (exit 4).
- Repeat rebuild deterministic.
- Headless.

Orbit/pan frame timing stays with the CAD host (FreeCAD) and the desktop contract; not this CLI.

## Upstream ask

OCCT: will you accept a public fixture list + DRAWEXE (or gtest) target that fails the build on crash/non-determinism?

FreeCAD: same via `FreeCADCmd` for ops exposed in Part.

If they take it, LET does not incubate.
