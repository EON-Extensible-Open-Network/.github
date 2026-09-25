# Contributing to EON Stream

This file is the organisation-wide contribution guide. Every EON Stream repository links here;
repository-specific build instructions live in that repository's `README.md`.

Before anything else, read the [Code of Conduct](CODE_OF_CONDUCT.md). It includes one
project-specific rule about infringing content that is not optional.

## Project status

EON Stream is in **Faz 0** — foundations and risk reduction. There is no usable release yet.
The contracts in [`eon-stream-spec`](https://github.com/EON-Extensible-Open-Network/eon-stream-spec) are at `v0` and
**explicitly unstable**: they will break without a migration path until `v1`. If you are
building something on top of EON Stream today, expect to rewrite it.

The authoritative roadmap is the project plan in
[`eon-docs`](https://github.com/EON-Extensible-Open-Network/eon-docs). Numbered decisions in it (madde 1,
madde 22, …) are referenced throughout the code and these documents. When a discussion
reaches a decision, the plan is what gets updated — not a comment thread.

## How contributions are licensed

### Developer Certificate of Origin (DCO), not a CLA

Every commit must be signed off:

```
git commit -s -m "core: validate module manifest against schema v0"
```

This appends `Signed-off-by: Your Name <your@email>`, which certifies you wrote the
patch or have the right to submit it under the repository's license
([DCO 1.1](https://developercertificate.org/)). CI rejects unsigned commits.

We use the DCO rather than a CLA deliberately: you keep your copyright, and the project
gains no power to relicense your work later. The cost of that choice is that license
changes are effectively impossible after the fact — which is why the module exception
below exists from the very first commit.

### Per-repository licenses

| Repository | License | Note |
|---|---|---|
| `eon-stream-core`, `eon-stream-engine`, `eon-stream-app` | `GPL-3.0-or-later` **WITH** the EON Module ABI Exception 1.0 | See `LICENSE-EXCEPTION.md` in those repos |
| `eon-edu-server` | `AGPL-3.0-or-later` | No exception — it is a network service |
| `eon-stream-spec` | `Apache-2.0` | A specification must be freely implementable, including by other clients |
| `eon-stream-sdk` | `MIT` | Addon authors should never hit a licensing question |
| `eon-docs` | `CC-BY-SA-4.0` | Matches the default we recommend for materials (madde 16e) |
| `eon-stream-marketplace` | `CC0-1.0` (index data) / `Apache-2.0` (tooling) | |

By opening a pull request you license your contribution under the license of that
repository, including the module exception where it applies.

Every source file carries an SPDX header. `reuse lint` runs in CI:

```
// SPDX-License-Identifier: GPL-3.0-or-later
// SPDX-FileCopyrightText: 2026 EON contributors
```

## Branching and review

Trunk-based, with short-lived branches:

- `main` — always green, always releasable. Protected: no direct pushes, linear history,
  CI required.
- `feat/<short-slug>`, `fix/<short-slug>`, `docs/<short-slug>`, `spec/<short-slug>` —
  branch from `main`, rebase onto it, squash-merge back. Keep them under a week; a branch
  that cannot be merged in a week is usually two changes.
- `release/vX.Y` — cut only when a release needs backports. Tags are `vX.Y.Z`, signed.

Commit messages follow [Conventional Commits](https://www.conventionalcommits.org/)
with the component as scope:

```
feat(core): resolve addon manifests against api v0
fix(stream): keep sequential window aligned after seek
docs(spec): describe mirrors field in the package format
```

A breaking change is marked `!` (`feat(spec)!: rename catalog id field`) and must say in
the body which plan item it affects.

## What makes a pull request easy to merge

1. **One concern per PR.** A refactor plus a behaviour change is two PRs.
2. **It says what it is for.** Link the issue, or the plan item (`madde 15d`). "Why now"
   matters more than "what changed" — the diff already says what changed.
3. **Tests for behaviour, not for coverage.** New parsing or protocol behaviour needs a
   fixture; see `tests/fixtures/` in `eon-stream-core`.
4. **No new dependency without a reason in the PR body.** Each one is a supply-chain
   commitment (madde 37) and a license question (`cargo deny check`).
5. **No third-party service calls added silently.** The project sends no telemetry by
   default and never will (madde 36).

`cargo fmt`, `cargo clippy -- -D warnings`, and `cargo test` must pass. Run them locally;
CI is a safety net, not your test runner.

## Security issues

**Do not open a public issue.** See [SECURITY.md](SECURITY.md).

## Things that will be declined

Being explicit saves everyone's time:

- Telemetry, analytics, crash reporting that is on by default (madde 36).
- Bundling any content source or addon with the application (madde 9).
- Code-executing local plugins before the sandbox design exists (madde 4).
- Anything that makes the Edu build reach the open marketplace or accept arbitrary
  addon URLs (madde 22) — the CI symbol check will catch it anyway.
- Storing a Turkish national ID number, or any student data, on our side (madde 21, 31).
- Features that only work against Stremio's account or streaming-server endpoints
  (madde 1) — they are known-incompatible by design, not bugs to fix.

If you think one of these is wrong, the place to argue it is an issue against the plan
in `eon-docs`, not a pull request against the code.
