# Security Policy

## Reporting a vulnerability

**Do not open a public issue for a security problem.**

Report privately through either channel:

- GitHub private vulnerability reporting — the **Security** tab of the affected
  repository → *Report a vulnerability* (preferred: it keeps the report attached to the
  repo and gives us a CVE path).
- Email `security@eonstream.org` *(placeholder — set a real address before the first public
  release)*.

Please include: the affected repository and version or commit, what an attacker can
achieve, the steps to reproduce, and anything you know about scope. A proof of concept
helps; a working weaponised exploit is not needed and is better left out of the initial
report.

If the issue involves **student or institutional data** in a EON Edu deployment, say so
in the first line. Those reports jump the queue: an institution is the data controller for
that data (madde 29, Rol C) and may have its own statutory notification deadlines to meet.

## What to expect

| Stage | Target |
|---|---|
| Acknowledgement that a human has read it | 72 hours |
| Initial assessment: severity, affected versions, whether it is in scope | 7 days |
| Fix or documented mitigation for high-severity issues | 30 days |
| Coordinated public disclosure | 90 days, or sooner once a fix ships |

These are targets, not contractual guarantees. EON Stream is a small, non-commercial project
and says so honestly rather than promising an enterprise SLA it cannot staff. If a
deadline will slip, you will be told before it slips, not after.

We will credit you in the advisory and the changelog unless you ask us not to. There is
no bug bounty — there is no money in the project (madde 38).

## Supported versions

Faz 0: **nothing is supported yet.** There is no release, and `main` carries no security
guarantee. This table becomes meaningful at v1.

| Version | Supported |
|---|---|
| `main` | Best effort, no guarantee |
| v1.x | Planned: latest minor only |

## Scope

In scope, most interesting first:

- **Sandbox escape** — a local plugin or module reaching beyond the Module ABI or its
  declared permissions (madde 4).
- **Signature and update chain** — accepting an unsigned, wrongly signed, revoked, or
  downgraded module, package, or application update (madde 34, 39).
- **Edu isolation** — anything that lets an Edu build reach the open marketplace, add an
  arbitrary addon URL, or exfiltrate institutional material (madde 22, 27, 28a).
- **Role and permission enforcement** — acting beyond a role's scope, or a fake
  principal/teacher reaching student data (madde 17, 18).
- **Data exposure** — any path that sends viewing history, student data, or a national ID
  anywhere (madde 31, 36).
- **Malicious remote addon** — a hostile addon server causing memory corruption, path
  traversal, SSRF, or code execution in the client (madde 4).
- **Malicious package** — a crafted material package that escapes its extraction
  directory or bypasses the content-type and malware checks (madde 15b, 27b).
- Supply chain: a dependency or build step that can inject code into a release
  (madde 37).

Out of scope:

- Vulnerabilities in third-party addons themselves. Report those to their authors; tell
  us if the client should have defended against it.
- Vulnerabilities in mpv, FFmpeg, or librqbit — report upstream. Tell us if our
  configuration or bundling makes the impact worse.
- Content complaints and copyright takedowns. Those are a different process entirely
  (madde 12), not a security report.
- Missing hardening with no demonstrated impact, automated-scanner output without a
  described attack, denial of service by simply sending very large input, and social
  engineering of maintainers.

## Our own commitments

- Dependencies are pinned; `cargo deny check advisories` runs in CI (madde 37).
- Released artefacts are signed, and every published file's SHA256 is listed (madde 22).
- A malicious module or addon **version** can be revoked so clients refuse it (madde 34).
  We consider "we cannot revoke it" a vulnerability in itself.
- Security advisories are published in the affected repository and in the changelog, with
  the affected version range stated.

## Safe harbour

Research done in good faith under this policy is welcome, and we will not pursue action
over it. Please: use only your own test installation, do not touch anyone else's data or
a real school's deployment, do not run denial-of-service tests against shared
infrastructure, and give us the disclosure window above.
