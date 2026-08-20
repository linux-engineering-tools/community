# Governance

Process for this organization. No other charter.

## Repositories

| Repo | Role |
|---|---|
| [community](https://github.com/linux-engineering-tools/community) | Requirements, RFCs, specs, agent skills, this governance |
| Other org repos | Incubated tools that graduated from a spec |

Organization-wide defaults live in the [`.github`](https://github.com/linux-engineering-tools/.github) repository.

## Roles

- **Maintainers** merge to default branches, triage issues, and decide incubation.
- **Contributors** file requirements, comment, and open pull requests.
- The GitHub org owners are the current maintainer set.

Adding a maintainer: demonstrated, sustained work (merged PRs, triage, specs) and agreement from existing maintainers. Removing one: inactivity or repeated violation of [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md) / [`CONTRIBUTING.md`](CONTRIBUTING.md). Record the change in an issue and the org team membership.

## Decisions

- **Lazy consensus** on routine docs and labels: propose in a PR, merge if no maintainer objects after a reasonable wait.
- **Requirements** are accepted, rewritten, sent upstream, or closed by a maintainer. Capability language is required; clone-specs are closed.
- **Incubation** (new tool repo) requires an RFC issue, a spec under `specs/`, and an explicit maintainer decision that upstream is the wrong home. See [`agents/skills/incubate-tool/SKILL.md`](agents/skills/incubate-tool/SKILL.md).
- **License** for new LET tools: Apache License 2.0, unless contributing to an existing project that requires matching its license.

## Clean room

Maintainers reject contributions that appear derived from proprietary implementations. See [`CONTRIBUTING.md`](CONTRIBUTING.md). This is not legal advice.

## Agent contributions

Agent-authored issues and PRs are welcome if a human is named as accountable and the clean-room checklist is complete. Agents do not get a pass on DCO or IP rules.
