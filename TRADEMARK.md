# Trademark and Naming Policy

**Status: DRAFT.** Not yet reviewed by a lawyer (madde 13). No trademark has been
registered yet.

## The short version

**The code is free. The name is not.**

EON Stream is licensed under the GPL and you may fork it, modify it, and redistribute it — that
is the point. What you may not do is distribute your fork under **"EON"**, **"EON Stream"**,
**"EON Edu"**, or the EON logo, in a way that suggests it is the project's own release.

## What the names are

**EON** — *Extensible Open Network* — is the **umbrella**, not a product. Products are named
`EON <Product>`: today **EON Stream** (the media viewer) and **EON Edu** (the institutional
product). More may follow under the same umbrella (madde 42 of the plan).

This policy protects the **umbrella name first**. Protecting only product names would leave the
name everything else hangs from unguarded, which is the opposite of useful.

## Why this policy exists

This is not brand vanity. It closes a specific hole that the GPL leaves open.

The two products deliberately share one umbrella and one core (madde 32): the same package
format, the same addon API, the same viewer. A student downloads material at school and opens
it at home with the same engine; a teacher learns one creator tool. That shared identity is the
point — and it means the reputation is shared too. A public institution evaluating EON Edu will
search "EON" and judge whatever carries it.

A copyleft license protects the source. It does nothing about the name. Without this policy,
anyone could ship a fork bundled with infringing content sources, call it "EON", and there
would be no way to tell it apart from ours — burning EON Edu's credibility through an actor we
have no relationship with. That is the largest risk the shared umbrella creates, and this file
is its mitigation.

## What you may do without asking

- Say your software "is based on EON Stream", "is a fork of EON Stream", or "is compatible with
  EON Stream" — accurate, descriptive statements of fact, in ordinary type, not in your logo or
  product name.
- Use the name in articles, reviews, tutorials, talks, and academic work.
- Keep the name in unmodified builds you redistribute (a Linux distribution packaging our
  release, for example) — please track our releases and send packaging issues upstream.
- Use the name in a repository or directory name that is clearly a fork
  (`yourname/eon-fork`).

## What needs written permission

- Naming a **modified** build "EON", "EON Stream", "EON Edu", `EON <anything>`, or anything
  confusingly similar. Change the name and the application id; the project will not chase
  good-faith forks that do.
- Using the `EON <Product>` pattern for your own project, which reads as an official EON
  product even when no existing product name is reused.
- Using the logo or icon as the mark of your own product, service, or company.
- Any use that implies endorsement, official status, or partnership — in particular,
  anything presented to a school, a ministry, or a public procurement process.
- Registering the name, a translation, or a close variant as a trademark, company name, or
  domain, in any jurisdiction.
- Merchandise.

Ask by opening an issue in this repository, or emailing `trademark@eonstream.org`
*(placeholder)*. The default answer for non-commercial, non-confusing use is yes.

## EON Edu

"EON Edu" identifies the institutional build produced from this project's own
repositories and signed with the Edu signing key (madde 22, 34). A fork may not use it.

An institution running EON Edu on its own servers may say so freely — "Our school uses
EON Edu" is a statement of fact, not a trademark use.

## Third-party names

The reverse also binds us, and it is listed here so it is not forgotten.

EON Stream is compatible with the Stremio addon protocol and is **not affiliated with,
endorsed by, or connected to Stremio**. We describe that compatibility in plain words
("compatible with Stremio addons") and do not use Stremio's name or logo as a mark, in our
icons, or inside the application. The precise boundary of acceptable descriptive use is an
open legal question (madde 13, question 8) and this section will be updated when it is
answered.

The same care applies to every other name that may appear near this project — MEB, EBA,
e-Okul, e-Devlet, MEBBİS. Naming them describes an integration or an intention; it never
implies approval. Integration with public systems happens only through official channels
and with official permission (madde 20, 21).

## If this policy is violated

First step is a message asking for a change, with a reasonable deadline. This project is
not interested in aggressive enforcement against hobbyists, and will not send a lawyer at
a fork that simply forgot to rename.

The exception, stated plainly: a build distributed under the EON Stream name that bundles
infringing content sources gets no grace period. That case is the reason this file exists.
