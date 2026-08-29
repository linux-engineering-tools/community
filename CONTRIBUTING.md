# Contributing

This repository tracks **requirements** and **requests for comments (RFCs)**. Code for tools lives in other repos after a specification graduates. Read this file before opening an issue or pull request. Short forms: [`TERMS.md`](TERMS.md).

Agents: start at [`AGENTS.md`](AGENTS.md) and the matching skill under `agents/skills/`.

## File a requirement

Questions and “does this tool exist?” go to [Discussions](https://github.com/linux-engineering-tools/community/discussions) in the matching [space](SPACES.md) (Mechanical, Fabrication, Electronics, …). Do not open a requirement issue for catalog lookup.

Use the **Requirement** issue form. Accepted items show up on the [Requirements project](https://github.com/orgs/linux-engineering-tools/projects/1). A useful requirement states:

- Who needs it and what job they are doing
- Inputs and outputs, named as **open or published standards** (file formats, ISO/ASME/IEC/IPC numbers, G-code dialects)
- Observable acceptance tests
- Existing free and open-source software (FOSS) that almost does it, and why it does not (see [`catalog/README.md`](catalog/README.md)). Use the catalog **Forge** URL when you ask that project, not a mirror.
- Whether this should be an upstream patch or a new tool, and why

### Do not include

- Proprietary source, binaries, leaked manuals, or NDA material
- “Make it work like Product X / Feature Y” as the specification
- Internal names, menu trees, or unique layouts from commercial tools
- Screenshots of commercial UIs
- Reverse-engineering notes taken from proprietary binaries without a published spec

If you need to mention a commercial product at all, mention it once as *motivation* (“schools require a Windows-only suite”) and then describe the **capability**. Maintainers will rewrite or close issues that specify a clone.

## Clean room

LET implements from public specs and standards, not from proprietary implementations.

- Do not submit work derived from proprietary source, leaked documents, or decompiled commercial tools.
- The default is: **do not reverse-engineer binaries**. If a published standard exists, use it.
- If a binary must be studied, that person does not write the implementation (two-team clean room). This is exceptional and requires maintainer agreement **before** the work starts.
- Pull requests must include a DCO sign-off and the clean-room affirmation in the PR template.

Flag suspected IP problems with `ip:flagged`. Do not discuss the proprietary material in the thread; summarize the concern and stop.

## Upstream first

A new LET repo is a last resort. Before incubating:

1. Identify the existing project that should own the work.
2. Check whether they will take the change (issue, mailing list, or RFC there). Use the catalog **Forge** URL.
3. File an LET RFC only if they decline, are dormant, or the work does not belong there.

See [`GOVERNANCE.md`](GOVERNANCE.md) and [`agents/skills/incubate-tool/SKILL.md`](agents/skills/incubate-tool/SKILL.md).

When you add a catalog row: homepage in **Project**, canonical repository in **Forge**, display token in **Display** (`catalog/README.md`). Cite GUI display evidence on [`catalog/desktop.md`](catalog/desktop.md). Scan GitLab groups, Kitware, ONELAB, Savannah, and SourceForge as well as GitHub (`catalog/README.md`, Where to scan). Do not add a commercial-product catalog.

## Pull requests (this repo)

This repo is docs, issue forms, skills, and specs.

- One topic per PR
- Every commit: `Signed-off-by: Full Name <email@domain>` ([DCO 1.1](https://developercertificate.org/))
- Use your real name and a real email
- Fill the PR template, including the clean-room affirmation

## Conduct

[`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md). Stay on the engineering work.
