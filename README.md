# About the Intellectual Property Reserve License

The **Intellectual Property Reserve License (IPRL)** is a short, source-available
license for authors who want to publish a work openly while keeping all intellectual
property in it. The work stays a defined, attributable, verifiable asset — suitable for
IP registration, business valuation, or a **founder's capital contribution** when
starting a company — while anyone may read, run, and share it unchanged.

IPRL faces two ways. Toward the Open Source community, it keeps open habits: open code,
open contribution, an open and verifiable record of authorship, and a built-in path for
the Authors to carry the work over into a true Open Source license. Toward founders, it
is a formation instrument that makes open publication and venture funding lawful
together. It is deliberately not punitive: the Authors' protection lies in what is
reserved, not in penalties.

The license text is in [`IPRL_LICENSE.md`](IPRL_LICENSE.md). It is intentionally short
and built around three generic terms: **Author (Contributor)**, **Publication**, and
**Signed Publication**. It never mentions any concrete technology, yet it maps directly
onto modern publication practice — version control histories, signed commits and tags,
detached signatures, package releases.

---

## The Publication Model

IPRL rests on a simple, logically closed model of published work, built up in four
steps:

1. **A Publication, protected by its signature.** A work made publicly available is a
   *Publication*. It comes under the license when its Author signs it: the signature is
   the single act that proves authorship and applies the terms. The signature
   definition is technology-neutral — a signed commit, a signed tag, a detached
   signature on an archive, or a qualified electronic signature all satisfy it. What is
   not signed, the license does not protect.

2. **From one Publication to a series.** A work may grow: later Publications add to or
   revise earlier ones, and the series up to any point forms one cumulative
   Publication. The license applies at both levels — to each Signed Publication by
   itself and to the cumulative whole. Each Author owns their own Signed Publications;
   all Authors together own the cumulative work; using any part of the work is using
   every Signed Publication embodied in it. The chain of signatures travelling with the
   work is the entire ownership record — no separate registry is needed.

3. **Unsigned additions imply permission and carry no claim.** Whoever adds material to
   the work without signing it thereby implicitly allows its use as part of the work on
   the terms already established. Unsigned material gains no authorship and no
   protection, and nobody is obliged to defend rights in it. A later Signed Publication
   building on top confirms it as part of the work on the signing Author's authority.

4. **New authors join only by explicit signed acceptance.** A Signed Publication made
   by someone who is not yet an Author does not join the cumulative work by itself. An
   existing Author must explicitly accept it in a Signed Publication of their own — one
   that identifies the accepted contribution and states its acceptance. Only then does
   its maker become an Author. New ownership claims on the work can therefore never
   arise implicitly or unilaterally.

On top of this model, the public gets use and the Authors keep change: anyone may read,
study, run, and redistribute the work unchanged — commercially or not — with license,
signatures, and notices intact; private adaptation is allowed only to study the work or
to prepare an offer back to the Authors.

A picture of the model, with Publications `P1…P4` by Authors `A` and `B`:

```
A: P1 ── P2 ──────────── P4 ─▶  cumulative Publication = P1+P2+P3+P4
                 ╲       ╱      Authors = {A, B}
B:                P3 ───╯       (B's Signed Publication, explicitly accepted
                                 by A's signature in P4)
```

---

## Key Principles

- ✅ Free to **read, study, run, and use** the work unchanged, for any purpose,
  commercial or not.
- ✅ Free to **redistribute verbatim copies**, with license, signatures, and notices
  intact.
- ✅ Outside contributions are possible: a signed contribution makes its maker an
  **Author** once an existing Author explicitly accepts it with their own signature;
  unsigned material is usable on the work's terms and carries no claim.
- ❌ **Publishing modified or derivative versions** is prohibited; adaptation is
  allowed only privately, to study the work or prepare an offer to the Authors.
- ❌ **Removing or forging signatures or authorship notices** is prohibited.
- ✅ All intellectual property remains **with the Authors** — in each Signed
  Publication and in the whole. What is not granted is simply reserved: unlicensed use
  is a matter for ordinary authorship law, and no forfeiture or penalty clause hangs
  over users.

IPRL is **not an Open Source license** (it withholds modification rights by design),
but it is written to live alongside Open Source practice. The Authors may at any time,
acting together, publish the work under an Open Source license proper.

---

## Using IPRL for Your Project

The license itself mandates no tooling, file names, or formats. The steps below are one
practical way to satisfy it with common tools.

### 1. Add the license text

Copy `IPRL_LICENSE.md` into your repository as `LICENSE.md` (or `LICENSE`). Every
publication must include the license text or a durable reference to it; a license file
in the repository covers this.

### 2. Make your signing credential public

Any verifiable credential works: a GPG key on a key server, an SSH key on your hosting
profile, a key fingerprint on your website. Optionally list authors and their
credentials in an `AUTHORS` file for convenience — the license treats the signature
record itself as authoritative, so the file is informative, not normative.

### 3. Sign every publication

With git, configure commit signing once and every commit becomes a Signed Publication:

```bash
git config commit.gpgsign true          # GPG, or:
git config gpg.format ssh               # sign with your SSH key
git config user.signingkey <your-key>
```

Signed tags (`git tag -s`) or a detached signature on a release archive
(`gpg --detach-sign --armor release.tar.gz`) equally satisfy the definition for
snapshot-style publication outside a version control history.

### 4. Accepting contributions

- A contribution arriving as the contributor's **own signed work**: accept it
  explicitly with your own signature — for example, a signed merge commit whose message
  identifies the contribution and states its acceptance ("Accept signed contribution
  `<ref>` by `<name>`"). The contributor thereby becomes an Author. Merely continuing
  on top of it is not enough — acceptance of a new author must be explicit.
- An **unsigned** patch or suggestion: incorporate it in your own signed commit — it is
  published on your authority, and its offeror acquires no authorship.

### 5. Optional: per-file notices

A short header in each source file is a helpful notice, though the license does not
require one:

```
// Copyright (C) <year> <author>
// Distributed under the Intellectual Property Reserve License (IPRL) v2.0
// see LICENSE.md
```

---

## Transfer and Relicensing

An Author may transfer the rights in their Signed Publications — for example, to a
company as a founder's contribution in kind. The company then stands as an Author under
the license. All Authors acting together may also relicense the work (e.g., transition
to MIT or Apache-2.0 later). Record either step the same way the work itself is
published: as a signed declaration, for example a signed commit adding a
`RELICENSING.md` stating the decision, the date, and the parties.

---

## Changes from Earlier Texts

**From v1** (single-author, `LICENSE.md.asc`): signing moved from a one-time signature
on the license file to the publications themselves, so authorship of every part of the
work and of the whole is provable from the public record; multiple authors are
supported; commercial use of unchanged copies is now permitted.

**From the v2 prototype** (637 lines): same intent, a tenth of the text. The prototype
encoded the mechanism into the license — VCS and changeset definitions, a `CONTRIBUTORS`
registry with nomination/acceptance/removal procedures, a ratification protocol, and a
dormancy/fallback regime. The final v2 replaces all of that with the three generic
terms: the signature chain *is* the registry, an existing Author's explicit signed
acceptance *is* admission and ratification, and relicensing (including any open-source
transition) is left to the Authors' unanimous, signed decision rather than an automatic
dormancy clock.

---

## Legal Note

The text of the IPRL license and all accompanying instructions are released under
[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). You are free to copy,
adapt, and reuse them in your own projects without restriction.
