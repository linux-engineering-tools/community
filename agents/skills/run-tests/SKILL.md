---
name: run-tests
description: Prove a LET change. Use when finishing a PR, verifying docs or issue forms, or when the user runs /run-tests. This community repo has no application test suite.
---

# Prove a change

## This repository (`community`)

There is no application to test. Before claiming a docs/forms/skills change is done:

- Issue forms are valid YAML (GitHub will reject bad forms on push; check the file locally with a YAML parser)
- Links in markdown resolve to files that exist in the tree
- Skills still match `AGENTS.md` (one skill per task; no duplicated rule text)
- No commercial clone-spec or political language was introduced

## Future tool repos

- Every user-facing action has a non-interactive CLI
- Tests run headless; GUI clicks are not the only proof
- Fixtures are open formats (STEP, DXF, G-code, BOM CSV, etc.) in-tree
- Do not claim Omarchy/Wayland GUI verification unless it was actually run on that stack
- Record the exact commands in the PR template
