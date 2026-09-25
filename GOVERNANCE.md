# Governance

EON Stream is open source and non-profit. This file says who decides what, so that the answer
is written down before it is contested rather than after.

**Current state, stated plainly:** the project has a single maintainer and no legal
entity. Everything below describes how it is meant to work as people join, and some of it
is aspirational today. Pretending otherwise would be the kind of thing this file exists to
prevent.

## Roles

**Contributor** — anyone who opens an issue or pull request. No formal status needed.

**Maintainer** — has merge rights on one or more repositories. Reviews, merges, and is
accountable for that repository staying green. Added by agreement of the existing
maintainers after a sustained contribution history (not after one good PR). Steps down by
saying so; inactive for six months with no word, the commit bit is removed — reversible on
request, with no hard feelings.

**Plan owner** — holds the project plan (`eon-docs/plan/eon-plan.md`) and is the
tiebreaker on scope. Today: the founding maintainer. This role exists because the plan's
numbered decisions are the project's memory, and a document with no owner rots.

**Release manager** — cuts releases and holds access to the signing keys for one channel
(madde 34). Deliberately separable from Maintainer: merge rights and signing rights are
not the same power.

## How decisions are made

Ordinary changes: lazy consensus. Open a PR; if a maintainer approves and nobody objects,
it merges. Silence is agreement.

**Decisions that change the plan** — architecture, scope, a new dependency with legal
weight, anything touching the legal or data-protection sections — work differently:

1. Open an issue in `eon-docs` titled `madde N: <what changes>`.
2. State the current decision, the proposed one, and what it costs. "What it costs" is
   required; a proposal with no stated downside has not been thought through.
3. Leave it open at least 7 days if anyone other than the proposer is affected.
4. On agreement, the plan item is updated **in the same pull request as the code**. Code
   that contradicts the plan is a bug in one of the two.

Plan items keep their numbers forever. Content changes, numbers do not.

**Deadlock** is broken by the plan owner, who must write the reason in the issue. An
unexplained tiebreak is not a decision, it is an instruction — and this project cannot
pay anyone to follow instructions.

## Things that are not up for lazy consensus

These require an explicit, recorded decision, and some of them require more than this
project currently has:

- **Relicensing.** Effectively impossible under the DCO (see `CONTRIBUTING.md`). That is
  the intended outcome, not an oversight.
- **Signing key custody and revocation** (madde 34). Emergency revocation needs a named
  procedure, not a judgement call at 3am.
- **Opening the marketplace backend.** Gated by a five-item checklist (madde 30, Faz L1)
  including a legal entity, legal review, and at least two human moderators. The gate
  exists specifically so that enthusiasm cannot open it early.
- **Anything that processes personal data**, especially student data (madde 31).
- **Accepting money** in any form (madde 38). Until there is a legal entity, the project
  takes no donations — an individual holding project funds is a problem, not a solution.
- **Using the project name** for anything official. See `TRADEMARK.md`.

## Legal entity

The project will need one before Faz L1 (madde 30). Comparison of the options — dernek,
şirket, or an external fiscal host — lives in madde 38 of the plan and is an open
question, not a settled one.

Until then: the signing keys and any domain names are held by the founding maintainer as
an individual. This is a known single point of failure, recorded here rather than hidden.
Custody moves to the legal entity the moment it exists.

## Moderation of project spaces

Code of Conduct enforcement is handled by maintainers (`CODE_OF_CONDUCT.md`). Marketplace
content moderation is an entirely separate system with its own audit log, appeal route,
and transparency report (madde 6, 12) — a maintainer's judgement about a rude comment and
a decision to remove someone's published work are not the same kind of power and do not
share a process.

## Changing this file

Same as any plan change: a pull request, 7 days, and a reason. Governance that can be
changed quietly is not governance.
