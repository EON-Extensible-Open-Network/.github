## What and why

<!-- What changes, and why now. The diff already shows what; explain why. -->

Relates to: <!-- #issue, or a plan item such as "madde 15d" -->

## How it was verified

<!-- Tests added, manual steps, platforms checked. "CI is green" is not verification. -->

## Checklist

- [ ] Commits are signed off (`git commit -s`) — DCO, see CONTRIBUTING.md
- [ ] `cargo fmt --check`, `cargo clippy -- -D warnings`, `cargo test` pass locally
- [ ] SPDX header present on new files
- [ ] New dependencies justified in this PR body (or none added)
- [ ] No telemetry, analytics, or default-on network calls introduced (madde 36)
- [ ] If this changes a contract in `eon-stream-spec`, the schema and its version are updated
- [ ] If this changes a decision, the plan item in `eon-docs` is updated in this PR

## Breaking changes

<!-- None, or: what breaks, who it affects, and the migration path. v0 contracts may
     break freely (see CONTRIBUTING.md) but the break must still be described. -->
