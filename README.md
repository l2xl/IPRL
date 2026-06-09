# About the Intellectual Property Reserve License

The **Intellectual Property Reserve License (IPRL)** is a short, source-available
license for authors who want to publish a work openly while keeping all intellectual
property in it. The work stays a defined, attributable, verifiable asset — suitable for
IP registration, business valuation, or a **founder's capital contribution** when
starting a company — while anyone may read, run, and share it unchanged.

The license text is in [`IPRL_LICENSE.md`](IPRL_LICENSE.md). It is intentionally short
and built around three generic terms: **Author (Contributor)**, **Publication**, and
**Signed Publication**. It never mentions any concrete technology, yet it maps directly
onto modern publication practice — version control histories, signed commits and tags,
detached signatures, package releases.

---

## The Incremental Publication Model

IPRL rests on a simple, logically closed model of how published works actually grow:

1. **A work is published as a series of increments.** The first release and every later
   addition or revision is a *Publication*. The cumulative work formed by the
   increments up to any point is also a *Publication*. Rights, conditions, and remedies
   therefore attach at both levels: to each iteration by itself and to the whole as the
   sum of iterations.

2. **A signature binds authorship to each increment.** A *Signed Publication* is an
   increment carrying a record that identifies its maker, shows the intent to publish
   under the license, and is verifiable by anyone against a public credential. The
   definition is technology-neutral: a signed commit, a signed tag, a detached
   signature on an archive, or a qualified electronic signature all satisfy it.

3. **The chain of signatures is the ownership record.** No separate registry is
   needed: the sequence of Signed Publications travels with the work and proves who
   created which increment, and who together created the whole. Each Author owns their
   own increments; all Authors together own the cumulative work. Using any part of the
   work is using every signed increment embodied in it — this is what protects both
   the iteration and the sum.

4. **Authorship propagates by signed continuation.** The maker of the first Signed
   Publication is the first Author. A new contributor becomes an Author exactly when an
   existing Author incorporates, or builds on, the contributor's own Signed
   Publication. Signing expresses acceptance of the license; continuing on top of
   someone's signed work expresses acceptance of that person. Nobody can join the
   authorship of a work unilaterally, and nobody joins it unknowingly.

5. **Unsigned contributions merge into the incorporating signature.** Material offered
   without a signature (a patch, a suggestion) is published on the authority of the
   Author who incorporates it. The offeror grants the necessary rights by offering and
   acquires no authorship. This lets maintainers accept outside fixes without diluting
   the ownership record.

6. **The public gets use; the Authors keep change.** Anyone may read, study, run, and
   redistribute the work unchanged — commercially or not — with the license,
   signatures, and notices intact. Private adaptation is allowed only to study the work
   or to prepare an offer back to the Authors. Publishing modified versions is reserved
   to the Authors, which is what keeps the work a bounded IP asset.

A picture of the model, with increments `P1…P4` by Authors `A` and `B`:

```
A: P1 ──── P2 ──────────── P4 ─▶  cumulative Publication = P1+P2+P3+P4
                  ╲       ╱       Authors = {A, B}
B:                 P3 ───╯        (B's Signed Publication, built upon by A in P4)
```

---

## Key Principles

- ✅ Free to **read, study, run, and use** the work unchanged, for any purpose,
  commercial or not.
- ✅ Free to **redistribute verbatim copies**, with license, signatures, and notices
  intact.
- ✅ Outside contributions are possible: signed ones make you an **Author** when
  incorporated; unsigned ones merge on the incorporating Author's authority.
- ❌ **Publishing modified or derivative versions** is prohibited; adaptation is
  allowed only privately, to study the work or prepare an offer to the Authors.
- ❌ **Removing or forging signatures or authorship notices** is prohibited.
- ✅ All intellectual property remains **with the Authors** — per increment and in the
  whole — with automatic termination on breach and a single 30-day cure.

IPRL is **not an Open Source license** (it withholds modification rights by design).
The Authors may at any time, acting together, additionally publish the work under an
Open Source license.

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

### 3. Sign every increment you publish

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

- A contribution arriving as the contributor's **own signed work**: merge it or build
  on it with your next signed commit — the contributor thereby becomes an Author.
- An **unsigned** patch or suggestion: incorporate it in your own signed commit — it is
  published on your authority and the offeror acquires no authorship.

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

An Author may transfer the rights in their increments — for example, to a company as a
founder's contribution in kind. The company then stands as an Author under the license.
All Authors acting together may also relicense the work (e.g., transition to MIT or
Apache-2.0 later). Record either step the same way the work itself is published: as a
signed declaration, for example a signed commit adding a `RELICENSING.md` stating the
decision, the date, and the parties.

---

## Changes from Earlier Texts

**From v1** (single-author, `LICENSE.md.asc`): signing moved from a one-time signature
on the license file to the publication increments themselves, so authorship of every
iteration and of the whole is provable from the public record; multiple authors are
supported; commercial use of unchanged copies is now permitted.

**From the v2 prototype** (637 lines): same intent, a tenth of the text. The prototype
encoded the mechanism into the license — VCS and changeset definitions, a `CONTRIBUTORS`
registry with nomination/acceptance/removal procedures, a ratification protocol, and a
dormancy/fallback regime. The final v2 replaces all of that with the three generic
terms: the signature chain *is* the registry, incorporation *is* admission and
ratification, and relicensing (including any open-source transition) is left to the
Authors' unanimous, signed decision rather than an automatic dormancy clock.

---

## Legal Note

The text of the IPRL license and all accompanying instructions are released under
[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). You are free to copy,
adapt, and reuse them in your own projects without restriction.
