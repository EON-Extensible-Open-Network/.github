# `.github` — EON organisation defaults

> **Push this directory to a repository named exactly `.github`** in the `eon`
> organisation. GitHub reads organisation-wide defaults from that name; any other name
> and none of this takes effect.

## What is here

| Path | Effect |
|---|---|
| `profile/README.md` | Rendered on the organisation's public page — the project's front door |
| `CONTRIBUTING.md` | Default contribution guide for every repo that has none of its own |
| `CODE_OF_CONDUCT.md` | Contributor Covenant 2.1 + the project's content rule (madde 29) |
| `SECURITY.md` | Vulnerability reporting, scope, disclosure targets |
| `GOVERNANCE.md` | Roles, how decisions are made, what is not up for lazy consensus |
| `TRADEMARK.md` | The name policy — the gap the GPL leaves open (madde 32d) |
| `.github/ISSUE_TEMPLATE/` | Bug and feature forms, plus routing for security and takedowns |
| `.github/PULL_REQUEST_TEMPLATE.md` | Default PR checklist |

Repository-specific `CONTRIBUTING.md` or issue templates override these; that is intended
for build instructions, not for policy.

## Before the first public push

Three placeholders must become real addresses, or the policies promise a channel that
does not exist:

- `conduct@` — `CODE_OF_CONDUCT.md`
- `security@` — `SECURITY.md`
- `trademark@` — `TRADEMARK.md`

Until a legal entity exists (madde 30, Faz L1) these can be aliases on any domain the
maintainer controls. What matters is that mail sent to them is read.

## Recommended organisation settings

- Default branch `main`; branch protection on `main` in every repo: require PR, require
  status checks, linear history, no force push.
- Require signed-off commits (DCO app) and enable **private vulnerability reporting** per
  repo — `SECURITY.md` points at it.
- Enable Dependabot alerts and secret scanning everywhere.
- Turn on organisation Discussions: `ISSUE_TEMPLATE/config.yml` routes questions there.

## License

`CC0-1.0` for the files in this repository, so any project may reuse these templates.
The Code of Conduct is Contributor Covenant 2.1, under `CC-BY-4.0`.
