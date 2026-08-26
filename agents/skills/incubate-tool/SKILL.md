---
name: incubate-tool
description: Graduate a LET spec into a new org repository. Use when creating a tool repo, when a requirement is ready to leave the board, or when the user runs /incubate-tool.
---

# Incubate a tool

A new repository is a last resort. Do this only after a maintainer decision on a request for comments (RFC). Spell out a term on first use in the new README, or link community [`TERMS.md`](https://github.com/linux-engineering-tools/community/blob/main/TERMS.md).

## Gates (all required)

1. **Requirement** issues exist, in capability language, `ip:clean`
2. **Public spec** under `specs/<name>/` (problem, standards, CLI, tests, license)
3. **Upstream check** documented: existing project named, asked, declined or wrong home (see `catalog/README.md`)
4. **RFC** issue approved by a maintainer
5. If GUI: desktop contract in the spec (`agents/skills/omarchy-desktop/SKILL.md`)

If any gate is missing, stop and file or finish that work here. Do not create the repo.

## New repo

- Under `github.com/linux-engineering-tools/<name>`
- Public, Apache License 2.0 (unless matching a required upstream license for a fork/patch repo — prefer not forking)
- Copy `AGENTS.md` pointer pattern, `CODE_OF_CONDUCT.md`, DCO PR template, `SECURITY.md` with private reporting enabled
- Enable Issues only for **that tool’s bugs**. New capabilities still go to `community`
- CLI with `--help`, stable exit codes, JSON where lists are returned
- Headless tests and fixtures in-tree
- No CLI named `let` (shell builtin). Use `let-<tool>` or similar

Do not add the new codebase to `community`.

## After create

Link the RFC and spec from the new README. Set the RFC issue to `status:incubating`. Do not announce a replacement for a named commercial product.
