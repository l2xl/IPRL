# About the Intellectual Property Reserve License

The **Intellectual Property Reserve License (IPRL)** is a short, source-available
license for authors who want to publish a work openly while keeping all intellectual
property in it. The work stays a defined, attributable, verifiable asset — suitable for
IP registration, business valuation, or a **founder's capital contribution** when
starting a company — while anyone may read, run, and share it unchanged.

IPRL faces two ways. Toward the Open Source community, it keeps open habits: open code,
open contribution, an open and verifiable record of authorship, and a built-in path for
the Rightsholders to carry the work over into a true Open Source license. Toward
founders, it is a formation instrument: open publication and the use of the sources as
a funding asset become legally compatible.

The license text is in [`IPRL_LICENSE.md`](IPRL_LICENSE.md). It is intentionally short
and built around a few generic terms: **Publication**, **Signed Publication**,
**Contributor**, and **Rightsholder**. It never mentions any concrete technology, yet
it maps directly onto modern publication practice — version control histories, signed
commits and tags, detached signatures, package releases.

Three notions that usually blur into the one word *author* are kept distinct: the
**author** in the ordinary sense (whoever made something — a fact no license can move),
the **Contributor** (an author whose Signed Publication is recognized as part of the
work), and the **Rightsholder** (whoever currently holds the **Reserved Rights** — the
economic rights in the work — the author at first, a successor after a transfer). Being
a Contributor is recognition of authorship; it does not by itself make one a
Rightsholder, and authorship is never among the Reserved Rights.

---

## The Publication Model

IPRL rests on a simple, logically closed model of published work, built up in four
steps:

1. **A Publication, protected by its signature.** A work made publicly available is a
   *Publication*. It comes under the license when its maker signs it: the signature is
   the single act that proves authorship and applies the terms — a deliberate act of
   signing, uniquely linked to the maker, under their sole control, and verifiable by
   anyone against something they have made public. The definition is technology-neutral —
   a signed commit, a signed tag, a detached signature on an archive, or a qualified
   electronic signature all satisfy it; a mark that merely names who made or uploaded
   something is attribution, not a signature. What is
   not signed, the license does not protect.

2. **From one Publication to a series.** A work may grow: later Publications add to or
   revise earlier ones. The whole set of Publications up to any point — signed, and
   some perhaps unsigned — is called the *Cumulative Work*. The name exists for
   clarity, not as a separate object of licensing: the license attaches to the Signed
   Publications, and protection of the whole follows from them, because using any part
   of the Cumulative Work is using every Signed Publication embodied in it. The
   **Reserved Rights** — the economic rights — in every Signed Publication belong to the
   work's Rightsholders, while authorship belongs always to its author; the chain of
   signatures travelling with the work is the entire ownership record, so no separate
   registry is needed.

3. **Unsigned additions join the work and raise no competing claim.** An addition
   published without a signature simply becomes part of the work as it was published —
   whoever publishes it lets it stand there on the work's terms. Its maker remains the
   author of what they made, as the law has it, but becomes a *Contributor* — recognized
   by the license — only through explicit signed acceptance (step 4). By letting an
   unsigned addition stand in the work, its maker grants the Rightsholders an exclusive,
   irrevocable license to the Reserved Rights in it, keeping authorship alone, so the
   work's Reserved Rights stay whole and no competing ownership claim can arise.

4. **New contributors join only by explicit signed acceptance.** A Signed Publication
   made by someone who is not yet a Contributor does not join the Cumulative Work by
   itself. An existing Contributor must explicitly accept it in a Signed Publication
   of their own — one that identifies the accepted Signed Publication and states its
   acceptance. Only then does its maker become a Contributor, retaining authorship of
   what they made; the Reserved Rights in the contribution vest in the work's
   Rightsholders. New ownership claims on the work can therefore never arise implicitly
   or unilaterally.

On top of this model, the public gets use and the Rightsholders keep change: anyone may
read, study, run, and redistribute the work unchanged — commercially or not — with
license, signatures, and notices intact; private adaptation is allowed only to study
the work or to prepare an offer back to the Rightsholders.

A picture of the model, with Publications `P1…P4` by Contributors `A` and `B`:

```
A: P1 ── P2 ──────────── P4 ─▶  Cumulative Work = P1+P2+P3+P4
                 ╲       ╱      Contributors = {A, B}   Rightsholders = {A}
B:                P3 ───╯       (B's Signed Publication, explicitly accepted by A
                                 in P4: B becomes a Contributor; the Reserved Rights
                                 in P3 vest in the Rightsholder A)
```

---

## Key Principles

- ✅ Free to **read, study, run, and use** the work unchanged, for any purpose,
  commercial or not.
- ✅ Free to **redistribute verbatim copies**, with license, signatures, and notices
  intact.
- ✅ Outside contributions are possible: a signed contribution makes its maker a
  **Contributor** once an existing Contributor explicitly accepts it with their own
  signature, while the **Reserved Rights** in it vest in the work's Rightsholders;
  unsigned additions become part of the work and raise no competing claim.
- ❌ **Publishing modified or derivative versions** is prohibited; adaptation is
  allowed only privately, to study the work or prepare an offer to the Rightsholders.
- ❌ **Removing or forging signatures or authorship notices** is prohibited.
- ✅ A **patent license** travels with every Signed Publication: its maker licenses, to
  the Rightsholders and to everyone using the work, any patent claims of theirs the
  Publication necessarily infringes — and bringing patent litigation over the work ends
  that license.
- ✅ All **Reserved Rights** remain **with the Rightsholders** — in each Signed
  Publication and in the whole; authorship always stays with its author and is never a
  Reserved Right. What is not granted is simply reserved.

IPRL is **not an Open Source license** (it withholds modification rights by design),
but it is written to live alongside Open Source practice. The Rightsholders may at any
time, acting together, publish the work under an Open Source license proper.

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

- A contribution arriving as the contributor's **own signed work**: an existing
  Contributor accepts it explicitly with their own signature — for example, a signed
  merge commit whose message identifies the contribution and states its acceptance
  ("Accept signed contribution `<ref>` by `<name>`"). Its maker thereby becomes a
  Contributor and keeps authorship of what they made, while the Reserved Rights in the
  contribution vest in the work's Rightsholders. Merely continuing on top of it is not
  enough — acceptance of a new contributor must be explicit.
- An **unsigned** patch or suggestion: incorporate it as you see fit — published
  unsigned, it stands as part of the work; its maker stays the author of the patch but
  does not become a Contributor, and by letting it stand grants the Rightsholders an
  exclusive license to the Reserved Rights in it.

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

A Rightsholder may transfer their rights — for example, to a company as a founder's
contribution in kind. The company then takes their place as Rightsholder under the
license; the transfer moves the reserved rights, not authorship, so the record of who
made what stands. All Rightsholders acting together may also relicense the work (e.g.,
transition to MIT or Apache-2.0 later). Record either step the same way the work itself
is published: as a signed declaration, for example a signed commit adding a
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
dormancy/fallback regime. The final v2 replaces all of that with a few generic terms:
the signature chain *is* the registry, an existing Contributor's explicit signed
acceptance *is* admission and ratification, and relicensing (including any open-source
transition) is left to the Rightsholders' unanimous, signed decision rather than an
automatic dormancy clock. The overloaded role of "Author" is split: a **Contributor**
made the work and always remains its author, but is not for that reason a Rightsholder;
the **Rightsholder** holds the **Reserved Rights** — the economic rights, which alone
can move — and the Reserved Rights in every accepted contribution vest in the work's
Rightsholders. A later edition makes the rights bundle explicit, adds a patent grant
with defensive termination, and records the author's consent to the changes the license
contemplates, so moral rights cannot be used to block them.

---

## Legal Note

The text of the IPRL license and all accompanying instructions are released under
[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). You are free to copy,
adapt, and reuse them in your own projects without restriction.
