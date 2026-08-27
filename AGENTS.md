# Agent instructions — linux-engineering-tools/community

Read this file before doing any work in this organization. Then open **one** skill from `agents/skills/` that matches the task. Do not copy skill text into this file. Spell out a term on first use, or link [`TERMS.md`](TERMS.md).

## What this org is

Public, clean-room requirements and incubation for Linux-native engineering tools. This repo is the issue board and specs. Code for tools lives in other org repos after a spec graduates.

## Hard rules

1. **Capability language.** Describe jobs, inputs, outputs, standards, and tests. Do not specify a clone of a named commercial product, UI, or feature.
2. **No proprietary IP.** No source, binaries, leaked docs, NDA workflows, commercial UI screenshots, or decompile notes. If an issue has that, stop and apply `ip:flagged`; do not expand on the material.
3. **Upstream first.** Check [`catalog/README.md`](catalog/README.md) before proposing a new tool.
4. **Wayland / keybindings** for any graphical user interface (GUI): native Wayland; shortcuts live in a simple user config file so users can avoid OS conflicts. Defaults use Ctrl / Shift / Alt. See `agents/skills/omarchy-desktop/SKILL.md`.
5. **Stay on engineering.** Do not add political, ideological, or identity language to docs, issues, or commit messages.
6. **Developer Certificate of Origin (DCO).** Commits need `Signed-off-by: Full Name <email>`.
7. **Terms.** First mention in a document uses the expanded form; [`TERMS.md`](TERMS.md) is the legend.
8. **Human accountable.** Agent-authored work must name the human who will answer for it.

## Skills (open the matching one)

| Task | Skill |
|---|---|
| File or triage a requirement issue | [`agents/skills/file-requirement/SKILL.md`](agents/skills/file-requirement/SKILL.md) |
| Review an issue or PR for IP | [`agents/skills/clean-room-review/SKILL.md`](agents/skills/clean-room-review/SKILL.md) |
| GUI, shortcuts, Wayland, Hyprland | [`agents/skills/omarchy-desktop/SKILL.md`](agents/skills/omarchy-desktop/SKILL.md) |
| Graduate a spec into a new repo | [`agents/skills/incubate-tool/SKILL.md`](agents/skills/incubate-tool/SKILL.md) |
| Prove a change | [`agents/skills/run-tests/SKILL.md`](agents/skills/run-tests/SKILL.md) |

Grok project skills under `.grok/skills/` are symlinks to the same files.

## Where things live

- Requirements and RFCs: GitHub issues in this repo (use the issue forms)
- Specs: `specs/`
- Spaces (mechanical / fabrication / electronics / …): [`SPACES.md`](SPACES.md). Do not create a new repo or org per topic.
- Existing FOSS: `catalog/README.md` (space pages, including data and desktop)
- Terms (legend): [`TERMS.md`](TERMS.md)
- Process: `CONTRIBUTING.md`, `GOVERNANCE.md`, `CODE_OF_CONDUCT.md`

## Default branch work

This repo is markdown, YAML issue forms, and skills. Keep PRs small and on one topic. Do not add a CAD/CAM/FEA codebase here.
