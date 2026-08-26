# Upstream asks (copy-paste)

Do not incubate until each named project has a public ask, or a documented reason it is the wrong home. Record URLs on [RFC #21](https://github.com/linux-engineering-tools/community/issues/21).

Capability language only. No product clones.

## OpenCASCADE (STEP round-trip)

**Where:** GitHub Issues on [Open-Cascade-SAS/OCCT](https://github.com/Open-Cascade-SAS/OCCT) or the project’s documented tracker.

Title: `Public STEP AP242 assembly round-trip fixtures (counts + bbox)`

Body:

We maintain a Linux-native engineering-tools board (https://github.com/linux-engineering-tools/community). Requirement: https://github.com/linux-engineering-tools/community/issues/8

Ask: will OCCT host (or accept) a small public fixture suite that:

1. Imports a STEP AP242 assembly with two instances
2. Exports STEP again
3. Reports solid/instance counts, units, and bounding box as structured data (JSON or similar)
4. Fails non-zero if counts or bbox drift beyond a documented tolerance

This is a harness, not a request to reimplement the kernel. If you already have this as `DRAWEXE` tests, a pointer is enough and we will not duplicate it.

## FreeCAD (STEP / DXF host)

**Where:** FreeCAD GitHub issue, linking the OCCT ask.

Title: `CLI round-trip report for STEP AP242 and DXF fixtures`

Body: same job as above, plus DXF entity counts, invoked without the GUI (`FreeCADCmd`). If FreeCAD prefers this to live entirely in OCCT tests, say so.

## IfcOpenShell (IFC)

**Where:** IfcOpenShell tracker.

Title: `CLI IFC4 round-trip: entity counts and placements as JSON`

Body: fixture with IfcBeam + IfcColumn + one connection + one property set. Import → export → compare counts, GlobalIds, placements. LET issue: https://github.com/linux-engineering-tools/community/issues/14

## KiCad (IPC-2581)

**Where:** KiCad GitLab, manufacturing export.

Title: `CLI check of IPC-2581 export against fixture JSON (layers, nets, drills)`

Body: LET issue https://github.com/linux-engineering-tools/community/issues/15. Prefer IPC-2581; Gerber X3 + Excellon as documented fallback. No vendor CAM database.

## If they accept

Close or keep LET RFC #21 as `wont` / document “upstream-first”; contribute the fixtures there.

## If they decline or are the wrong home

Maintainer may accept RFC #21. Incubate only the harness; still call these libraries. Apache-2.0. Binary not named `let`.
