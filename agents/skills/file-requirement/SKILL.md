---
name: file-requirement
description: File or triage a LET requirements issue. Use when opening, rewriting, or reviewing a requirement; when an issue names a commercial product to copy; or when the user runs /file-requirement.
---

# File or triage a requirement

Use the **Requirement** issue form in this repo. Do not open a blank issue.

## Write the issue

Required substance (map to form fields):

- **Job** — who, what they are finishing, how often. No commercial feature names.
- **Inputs/outputs/standards** — published specs (STEP, DXF, ISO GPS, ASME Y14.5, IPC, G-code dialect). Not vendor-internal formats.
- **Acceptance tests** — observable, preferably CLI + fixtures.
- **Existing FOSS** — from `catalog/README.md`. Say whether this should go **upstream**.
- **GUI?** — if yes, the Omarchy desktop contract applies (`agents/skills/omarchy-desktop/SKILL.md`) before incubation.

Title: `[req] ` plus the job in a few words.

Labels: `type:requirement`, `status:needs-triage`, `domain:<name>`, `ip:clean` if the form checks passed.

`domain:eda` is schematic/PCB/simulation. `domain:bench` is instruments, capture, and repair (PSU, DMM, LA/scope, USB sniff, JTAG). Check [`catalog/electronics.md`](../../../catalog/electronics.md) first; sigrok and lxi-tools are the default upstreams for instruments.

## Rewrite product-named drafts

If the draft says “like Product X” or names a vendor feature:

1. Keep the **job** (what the engineer must finish).
2. Drop product, feature, and menu names.
3. Replace with standards and tests.
4. If that is impossible because the submitter only has a clone in mind, close as not a LET requirement and point at `CONTRIBUTING.md`.

Never paste the proprietary detail you are removing into a comment.

## Triage

| Observation | Action |
|---|---|
| Clone-spec or commercial UI screenshots | Close; `ip:flagged` |
| Proprietary source / NDA | Stop; `ip:flagged`; do not quote the material |
| Valid job, missing tests or standards | Ask for those; keep `status:needs-triage` |
| Existing FOSS can take it | Label `type:upstream`, `status:upstream-first`; link that project |
| Needs a spec before code | `status:needs-spec`; point at `specs/` |
| Agent-drafted, no human named | Ask for the accountable human; do not merge/accept without one |

Do not incubate a repo from a requirement issue. That is an RFC plus `agents/skills/incubate-tool/SKILL.md`.
