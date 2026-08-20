---
name: clean-room-review
description: Review LET issues and PRs for proprietary IP. Use when an issue or PR might contain commercial source, UI, leaked docs, NDA material, or clone-specs; or when the user runs /clean-room-review.
---

# Clean-room review

LET implements from public specs and standards. This skill is the IP check, not legal advice.

## Fail (stop, do not expand)

Apply `ip:flagged`, close or convert to a maintainer-only note, and **do not quote** the offending material:

- Proprietary source, binaries, or decompile/disassembly notes
- Leaked manuals or NDA workflows
- Screenshots or copies of commercial UIs (layout, unique control names, trade dress)
- A spec whose only content is “make it work like Product X / Feature Y”
- File-format reverse engineering from binaries when no published spec is cited

Comment with a short reason (“closed: clone-spec” / “closed: proprietary material”) and a link to `CONTRIBUTING.md`. Then stop.

## Pass

Apply `ip:clean` when all of these hold:

- Job is described as a capability with standards and tests
- Existing FOSS is considered
- No commercial UI or source is attached
- Clean-room checkboxes on the form are checked
- For PRs: DCO sign-off on every commit and the PR template affirmation is checked

## Two-team reverse engineering

Default: **do not**. If someone believes a binary must be studied:

1. They must get maintainer agreement **before** starting
2. The person who studies the binary **does not** write the implementation
3. Only a public spec (no verbatim proprietary text) may be handed to implementers

If that process was not followed, reject the work.

## PRs

Reject if commits lack `Signed-off-by`, if the author used anonymous email for code changes, or if the diff implements behavior that can only have come from a proprietary original rather than a public spec in `specs/` or a cited standard.
