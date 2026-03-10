# Intellectual Property Reserve License (IPRL)
**Version 2.0**

---

## Preamble

This License exists for a single primary purpose: to preserve the exclusive intellectual
property rights of its authors so that the Software may be used as a verifiable,
non-material asset — including as a founder's contribution when establishing a legal
entity, as an intangible asset in business valuation, or as registered IP in official
filings — while simultaneously making the source code publicly available for study and
non-commercial execution.

This License is a **source-available** license. It is intentionally not an Open Source
license under the Open Source Initiative (OSI) definition, because the modification and
commercial-use restrictions of Sections 6 and 7 are essential to its IP-preservation
purpose. A time-triggered, irrevocable transition to a fully Open Source license is
provided in Section 10 (Dormancy and Fallback) to protect the public interest in the
event of development cessation. The relationship to the Open Source Definition is
explained in Appendix D.

---

## 1. Definitions

**"Software"** means the collection of source code, documentation, data, and other
creative works governed by this License, as recorded in a Version Control System or
otherwise distributed.

**"Version Control System" (VCS)** means any system that records a history of changes
to files with author attribution, including but not limited to Git, Mercurial, and SVN.

**"Changeset"** means a discrete, atomic unit of change in a VCS — including a git
commit, Mercurial changeset, or SVN revision — that records modifications to the
Software with a cryptographically verifiable author identity.

**"Signing Key"** means a GPG/OpenPGP key pair, an SSH key pair, or an X.509
certificate used to produce cryptographic signatures on Changesets or files, where the
public portion is recorded in the Contributor Registry.

**"Authoritative Changeset"** means a Changeset that is cryptographically signed by a
Licensed Contributor using a Signing Key registered in the Contributor Registry at the
time the Changeset is made, such that the signature can be verified using standard VCS
tooling (e.g., `git verify-commit`) against the public key recorded in the Contributor
Registry.

**"Alien Changeset"** means any Changeset that is not an Authoritative Changeset — i.e.,
it is unsigned, or signed with a key not registered in the Contributor Registry.

**"Ratified Changeset"** means an Alien Changeset that has been explicitly accepted into
canonical history by an Authoritative Changeset in accordance with Section 5.

**"Contributor Registry"** means the authoritative, VCS-tracked list of Licensed
Contributors and their Signing Keys, maintained in a file named `CONTRIBUTORS.iprl` in
the root of the Software repository. The format is defined in Appendix B.

**"Licensed Contributor"** means any natural person or legal entity whose Signing Key is
recorded in the current Contributor Registry at the time a relevant Changeset is made.

**"Founding Contributor"** means the first Licensed Contributor to apply this License
to the Software, whose identity is established by the initial `LICENSE.md.asc` signature
described in Section 3.1.

**"Contributor Pool"** means the set of all current Licensed Contributors.

**"Dormancy Period"** means a continuous period of twenty-four (24) calendar months
during which no Authoritative Changeset has been added to the Software's canonical
version history in any publicly accessible repository.

**"Fallback License"** means the Apache License, Version 2.0, as published by the Apache
Software Foundation (https://www.apache.org/licenses/LICENSE-2.0).

**"You"** or **"User"** means any person or entity exercising rights under this License
who is not a Licensed Contributor.

---

## 2. Purpose and Scope

### 2.1 Primary Purpose

The sole purpose of this License is to preserve and document intellectual property
rights in a form suitable for:

- formal registration of intellectual property with governmental bodies;
- valuation as an intangible asset for accounting and business purposes;
- contribution as a founder's share or IP asset during formation of a legal entity;
- demonstration of authorship in investment due diligence or licensing negotiations.

This License's restrictions exist solely to serve this purpose. They are not intended to
impede legitimate study, non-commercial use, or the flow of knowledge.

### 2.2 Scope

This License governs the entire Software repository and all Changesets therein from the
date of the Foundational Signature (Section 3.1). It applies regardless of the platform
on which the VCS repository is hosted and operates on the raw VCS data, requiring no
platform-specific features.

---

## 3. Identification of Rightsholders

### 3.1 Foundational Signature

The Founding Contributor establishes this License by creating, in an Authoritative
Changeset:

(a) A file `LICENSE.md` containing the full text of this License;
(b) A file `LICENSE.md.asc` containing a detached cryptographic signature of `LICENSE.md`,
    produced with the Founding Contributor's Signing Key; and
(c) The initial `CONTRIBUTORS.iprl` file recording the Founding Contributor's entry.

The Founding Contributor's Signing Key must be capable of verification at the time of
the Foundational Signature and for a reasonable period thereafter.

### 3.2 Changeset-Based Attribution (Primary Mode)

When the Software is managed in a VCS, a Licensed Contributor's authorship of any
content is established by the existence of one or more Authoritative Changesets
introducing or modifying that content.

**When Changeset-Based Attribution is used, no per-file license header is required.**
The Authoritative Changeset signature serves as the license declaration and authorship
proof for all content introduced or modified by that Changeset.

To configure git commit signing for use with this License:

```
git config user.signingkey <KEY-ID-OR-PATH>
git config commit.gpgsign true
```

Signatures are verifiable using `git verify-commit <sha>` or `git log --show-signature`.

### 3.3 File Header Mode (Alternative / Snapshot Mode)

As an alternative to Changeset-Based Attribution, or when the Software is distributed
outside a VCS (e.g., as a source archive without commit history), a Licensed Contributor
must embed a license header in each source file using the format specified in Appendix A.

File Header Mode must be used when:

(a) The Software is distributed as a snapshot or archive without full VCS commit history; or
(b) Any file is distributed in isolation from its VCS context.

### 3.4 Key Integrity and Key Compromise

The use of a cryptographic Signing Key does not limit a Licensed Contributor's ability
to assert exclusive rights by other legally accepted means. In the event of key loss,
revocation, or compromise:

(a) The Licensed Contributor should create a new Authoritative Changeset with a new
    Signing Key updating their entry in `CONTRIBUTORS.iprl`, signed (if possible) with
    the old key or countersigned by another Licensed Contributor;
(b) Authorship of prior Authoritative Changesets remains valid and provable by the
    immutable VCS history and the content of those Changesets;
(c) A statutory declaration or other legally sufficient evidence of identity may be
    used to supplement cryptographic evidence in legal proceedings.

---

## 4. The Contributor Pool

### 4.1 Formation

The Founding Contributor constitutes the initial Contributor Pool. The `CONTRIBUTORS.iprl`
file is the sole authoritative source for Pool membership and must contain, for each
Licensed Contributor, the information specified in Appendix B.

### 4.2 Admission of New Contributors

A person or entity is admitted to the Contributor Pool only when **both** of the
following conditions are satisfied:

(a) **Nomination**: An existing Licensed Contributor creates an Authoritative Changeset
    that adds the nominee's entry (including their Signing Key) to `CONTRIBUTORS.iprl`; and

(b) **Acceptance**: The nominee, using their own Signing Key (which must now match the
    key recorded under their entry), creates a subsequent Authoritative Changeset that
    contains an explicit written acceptance of the terms of this License.

An entry in `CONTRIBUTORS.iprl` without a corresponding acceptance Changeset from the
nominee does not constitute admission. A nominee's acceptance Changeset simultaneously
constitutes their grant under Section 4.4.

### 4.3 Platform-Independent Registry

The `CONTRIBUTORS.iprl` file is the sole mechanism for defining the Contributor Pool.
Platform-level access controls (e.g., GitHub repository teams, GitLab project members)
do **not** automatically grant or imply Licensed Contributor status. Such lists may
serve as corroborating evidence of identity and intent but have no independent legal
effect under this License.

This design ensures that IPRL operates identically on any raw git repository, regardless
of hosting platform.

### 4.4 Intra-Pool Mutual Rights Grant

Each Licensed Contributor, by being admitted to the Pool, irrevocably grants to every
other current and future Licensed Contributor a **perpetual, worldwide, royalty-free**
license to:

(a) use, copy, modify, adapt, and create derivative works of the entire Software,
    including all Changesets contributed by the granting Contributor;
(b) compile, execute, deploy, and operate the Software for any commercial or
    non-commercial purpose;
(c) sublicense the Software to third parties solely under the terms of this License
    or a duly adopted successor version thereof.

This intra-pool grant is the mechanism by which collaborative development occurs without
fragmenting IP ownership. Each Licensed Contributor retains full copyright ownership of
their contributed Changesets; the grant is a license, not a transfer. The mutual,
exclusive-as-to-the-world nature of the grant preserves the IP value of the Software:
no person outside the Pool acquires modification or commercial-use rights, while every
Pool member has full operational rights.

### 4.5 Withdrawal of a Licensed Contributor

A Licensed Contributor may withdraw from the Pool by creating an Authoritative Changeset
explicitly declaring their withdrawal and updating `CONTRIBUTORS.iprl`. Withdrawal:

(a) does not retroactively revoke rights in Changesets made prior to withdrawal;
(b) does not affect the intra-pool grants already given, which remain irrevocable;
(c) terminates that Contributor's right to make future Authoritative Changesets binding
    on the Pool.

### 4.6 Removal by the Pool

A Licensed Contributor who has made no Authoritative Changeset for twelve (12) or more
consecutive calendar months may be removed from the Pool by an Authoritative Changeset
of any remaining Licensed Contributor, which must state the grounds and the period of
inactivity. Removal is effective upon creation of a subsequent Authoritative Changeset
by any other Licensed Contributor confirming the removal (two-step consensus). Removal
does not retroactively affect the removed Contributor's ownership of prior Changesets.

---

## 5. Alien Changesets

### 5.1 Effect on Authorship

An Alien Changeset does not grant any intellectual property rights to its author under
this License. The author of an Alien Changeset:

(a) does not become a Licensed Contributor;
(b) does not acquire any rights to the Software beyond those granted to Users under
    Section 6; and
(c) has no effect on the IP ownership claims of any Licensed Contributor.

### 5.2 Ratification

An Alien Changeset is Ratified — and thereby incorporated into the canonical Software
history without constituting a license breach — when a Licensed Contributor creates an
Authoritative Changeset that:

(a) **Is a direct successor**: the Authoritative Changeset's parent (in VCS graph terms)
    is the Alien Changeset or an unbroken chain of Alien Changesets; or

(b) **Contains an explicit reference**: the Authoritative Changeset explicitly identifies
    the Alien Changeset by its cryptographic identifier (e.g., git commit SHA) and
    includes a statement of acceptance (e.g., "Ratified: <sha>").

A Ratifying Licensed Contributor assumes responsibility for the content of the Ratified
Changesets as part of the canonical Software history. The Alien Changeset author acquires
no additional rights through Ratification.

### 5.3 Ratification Deadline

An Alien Changeset that is present in any publicly accessible repository and is not
Ratified within **ninety (90) calendar days** of its first public appearance must be
removed from the canonical history by any Licensed Contributor. Knowingly maintaining
or distributing the Software in a state containing unratified, overdue Alien Changesets
constitutes a breach of this License by the maintaining party.

Alien Changesets in private branches or forks, or in branches not yet merged into the
canonical main branch, are not subject to this deadline until the branch is merged or
publicly distributed as part of the Software.

### 5.4 Rationale

The Ratification mechanism allows external contributions (e.g., bug reports with patches,
community pull requests) to be accepted without requiring contributors to formally join
the Pool, while ensuring that a Licensed Contributor vouches for each such contribution
and the authorship record of the Software remains unambiguous.

---

## 6. Rights Granted to Users

Subject to all conditions and restrictions of this License, the Licensed Contributors
collectively grant to You a worldwide, royalty-free, non-exclusive, non-transferable,
non-sublicensable, irrevocable (except as provided in Section 9) license to:

(a) **Read and Study**: access, read, copy, and analyze the source code for any
    non-commercial educational or research purpose;

(b) **Compile and Execute**: compile the Software from source and execute or run the
    resulting binary or interpreted program for your own internal, non-commercial use;

(c) **Redistribute Unmodified**: distribute verbatim, unmodified copies of the Software
    in source or compiled form, provided that all of the following conditions are met:

    (i)   the full VCS history, including all Authoritative Changeset signatures, is
          preserved and cryptographically verifiable in any distributed VCS repository;
    (ii)  where File Header Mode is used, all headers are preserved intact and unmodified;
    (iii) `LICENSE.md`, `LICENSE.md.asc`, and `CONTRIBUTORS.iprl` are included and
          unmodified;
    (iv)  the recipient is notified that the Software is governed by this License; and
    (v)   no additional restrictions are imposed on recipients beyond those stated here.

**This License does not grant any right to modify, adapt, translate, or create derivative
works of the Software.**

**This License does not grant any right to use the Software or any part thereof for
commercial purposes.**

---

## 7. Restrictions

You are expressly prohibited from:

(a) **Modification**: modifying, adapting, translating, reverse-engineering for the purpose
    of creating competitive derivative works, or creating derivative works of the Software
    in any form;

(b) **Commercial Use**: using the Software or any portion thereof for commercial purposes,
    including but not limited to: incorporating it into a commercial product or service;
    using it to provide services to paying customers; using it to gain competitive
    commercial advantage; or deploying it in a production environment operated for profit;

(c) **Transfer of Rights**: sublicensing, selling, renting, leasing, or otherwise
    transferring Your rights in the Software to any third party;

(d) **Tampering with Attribution**: removing, obscuring, forging, or altering any license
    notices, Signing Key data, Authoritative Changeset signatures, `CONTRIBUTORS.iprl`,
    or `LICENSE.md.asc`;

(e) **False Ownership Claims**: using the Software in any manner that could be construed
    as asserting ownership over it by a party who is not a Licensed Contributor.

---

## 8. Exclusive Rights and Capital Contribution

### 8.1 Ownership Preserved

All copyright and intellectual property rights in each Licensed Contributor's
Changesets remain exclusively with that Licensed Contributor. This License does not
transfer ownership or any exclusive right to any person or entity other than through
the intra-pool mutual grant of Section 4.4.

### 8.2 IP Asset Use

Licensed Contributors may use the Software as:

- an object of intellectual property for official registration with patent, copyright,
  or trade secret authorities;
- an intangible asset for financial reporting and business valuation;
- a founder's contribution in kind upon formation of a legal entity;
- collateral or subject matter in licensing negotiations or investment due diligence.

### 8.3 Contribution to a Legal Entity

When a Licensed Contributor contributes the Software, or their rights therein, to a
legal entity (e.g., as a founder's IP contribution upon company formation):

(a) The contribution does not automatically modify the rights of other Licensed
    Contributors, whose intra-pool grants under Section 4.4 remain in force;
(b) The receiving legal entity steps into the shoes of that Licensed Contributor for
    purposes of the intra-pool mutual grant, becoming bound by this License as a
    Licensed Contributor;
(c) The contributing Licensed Contributor must create an Authoritative Changeset
    updating `CONTRIBUTORS.iprl` to record the legal entity as successor-in-interest
    to their entry, including the legal entity's authorized Signing Key(s).

---

## 9. Termination

### 9.1 Automatic Termination

Any breach of this License by You terminates your rights under Section 6 automatically
and without notice. The right to read source code (Section 6(a)) survives termination
for the sole purpose of allowing You to identify and remediate the breach.

### 9.2 Cure Period

Where a breach is capable of cure, You have thirty (30) calendar days from the date You
first have actual or constructive knowledge of the breach to cure it fully. Upon complete
cure, Your rights under Section 6 are reinstated automatically, once only. A second
breach of the same provision terminates rights permanently without a further cure period.

### 9.3 Remedies

Licensed Contributors may, individually or collectively:

(a) demand immediate cessation of infringing use and verifiable deletion or destruction
    of all unauthorized copies and derivatives;
(b) seek injunctive or other equitable relief without the requirement of posting bond;
(c) seek actual or statutory damages, including lost profits, as available under
    applicable copyright law;
(d) publish notice of violations where legally permissible.

---

## 10. Dormancy and Fallback License

### 10.1 Dormancy Trigger

The Software becomes **Dormant** upon the occurrence of either:

(a) **Automatic Dormancy**: no Authoritative Changeset has been added to any publicly
    accessible instance of the canonical repository for a continuous period of
    twenty-four (24) calendar months. The Dormancy date is twenty-four months after
    the last Authoritative Changeset's VCS timestamp; or

(b) **Voluntary Dormancy**: every Licensed Contributor listed in the then-current
    `CONTRIBUTORS.iprl` has separately created an Authoritative Changeset explicitly
    declaring the Software Dormant. Voluntary Dormancy takes effect upon the last
    such declaration.

### 10.2 Effect of Dormancy — Fallback License

Upon Dormancy, the Software is **automatically and irrevocably re-licensed** under the
**Apache License, Version 2.0** (the Fallback License), in addition to the rights
already granted under this License.

The Fallback License is granted to all persons worldwide, including the rights to use,
modify, distribute, and sublicense the Software commercially, subject to the attribution
and notice requirements of the Apache License, Version 2.0.

For the avoidance of doubt:

(i)  Licensed Contributors retain copyright ownership of their respective Changesets
     after Dormancy; the Fallback License is a license, not a transfer;
(ii) Licensed Contributors may not use this License to restrict any right granted by
     the Fallback License once Dormancy has occurred;
(iii) the Dormancy re-licensing is irrevocable and cannot be reversed even if
      development subsequently resumes;
(iv) the Apache License, Version 2.0 attribution requirements apply — downstream users
     must preserve copyright notices and `CONTRIBUTORS.iprl`.

### 10.3 Rationale for Apache 2.0 as Fallback License

The Apache License, Version 2.0 is selected as the Fallback License because:

(a) it satisfies the Open Source Definition of the Open Source Initiative (OSI),
    ensuring that upon Dormancy the Software becomes genuinely open source and freely
    usable by the community;
(b) it includes an explicit, royalty-free patent license grant, substantially reducing
    downstream litigation risk;
(c) it is broadly compatible with GPL v3, LGPL, MIT, BSD, and most other open source
    licenses, maximizing the reusability of the Software after Dormancy;
(d) its attribution requirements ensure that Licensed Contributors receive permanent
    credit for their work even after Dormancy.

### 10.4 Legal Basis for Time-Triggered Relicensing

The Automatic Dormancy mechanism is modeled on the "Change Date" mechanism of the
Business Source License (BSL 1.1) and analogous time-limited restrictions recognized
in contract law across multiple jurisdictions. A license grant conditioned on the
licensor's inaction for a defined period is a valid, enforceable contractual term in
jurisdictions following both common law and civil law traditions. The twenty-four month
Dormancy Period is calibrated to be short enough to protect the public interest while
long enough to accommodate ordinary gaps in active development.

---

## 11. Jurisdiction and Electronic Signatures

This License applies globally under international copyright treaties including the
Berne Convention, the TRIPS Agreement, and the WIPO Copyright Treaty.

The cryptographic signatures described in this License constitute valid and binding
electronic signatures under:

- Regulation (EU) No 910/2014 (eIDAS) — as advanced electronic signatures;
- the U.S. Electronic Signatures in Global and National Commerce Act (E-SIGN);
- the UNCITRAL Model Law on Electronic Signatures;
- and equivalent national legislation in other jurisdictions.

A cryptographic signature on a Changeset or on `LICENSE.md.asc` is legally equivalent
to a handwritten signature on a document asserting authorship and acceptance of these
terms.

National appendices may be issued by Licensed Contributors for local compliance without
affecting the global applicability of this License.

---

## 12. Disclaimer of Warranties and Limitation of Liability

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED,
INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR
PURPOSE, TITLE, AND NON-INFRINGEMENT.

IN NO EVENT SHALL ANY LICENSED CONTRIBUTOR BE LIABLE FOR ANY CLAIM, DIRECT, INDIRECT,
INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING BUT NOT LIMITED TO
LOSS OF DATA, LOSS OF PROFITS, OR BUSINESS INTERRUPTION), HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT, ARISING FROM OR
IN CONNECTION WITH THE SOFTWARE OR THIS LICENSE, EVEN IF ADVISED OF THE POSSIBILITY
OF SUCH DAMAGES.

---

## 13. License of This Document

The text of this License (`LICENSE.md`), the `CONTRIBUTORS.iprl` format specification
(Appendix B), and all accompanying templates and documentation are released under the
**Creative Commons Zero v1.0 Universal (CC0)** license. You are free to copy, modify,
distribute, and use them without restriction, for any purpose, without asking permission.

---

## Appendix A: File Header Format (File Header Mode)

Use language-appropriate comment syntax. Include at minimum the license name and a
reference to `CONTRIBUTORS.iprl`. The full public key may be included for snapshot
distributions where the VCS history is not available.

```
// [Optional copyright notice, e.g.: Copyright (C) 2024 Alice Smith]
// Distributed under the Intellectual Property Reserve License (IPRL) v2.0
// Licensed Contributors: see CONTRIBUTORS.iprl
//
// [Include the following block only in snapshot/archive distributions:]
// GPG Public Key of contributing author:
// -----BEGIN PGP PUBLIC KEY BLOCK-----
// [key here]
// -----END PGP PUBLIC KEY BLOCK-----
```

---

## Appendix B: CONTRIBUTORS.iprl Format

The `CONTRIBUTORS.iprl` file uses TOML syntax and must be maintained as an Authoritative
Changeset. The file is the sole authoritative Contributor Registry. Example:

```toml
# CONTRIBUTORS.iprl — Licensed Contributor Registry
# Governed by the Intellectual Property Reserve License (IPRL) v2.0
# This file is authoritative only when it exists in an Authoritative Changeset.
# Last modified: <ISO 8601 date> by <contributor name>

license_version = "2.0"
repository = "https://example.com/org/repo"   # optional canonical URL

[[contributor]]
name          = "Alice Smith"
email         = ["alice@example.com"]
admitted      = "2024-01-15"   # ISO 8601 date of acceptance Changeset
accepted_sha  = "abc123def456" # SHA of the contributor's own acceptance Changeset

  [[contributor.signing_keys]]
  format      = "gpg"
  fingerprint = "ABCD 1234 5678 9ABC DEF0  1234 5678 9ABC DEAD BEEF"
  pubkey      = """
-----BEGIN PGP PUBLIC KEY BLOCK-----
[ASCII-armored key here]
-----END PGP PUBLIC KEY BLOCK-----
"""

  [[contributor.signing_keys]]
  format      = "ssh"
  pubkey      = "ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAI... alice@example.com"

[[contributor]]
name          = "Bob Jones"
email         = ["bob@example.com", "bob@work.example.com"]
admitted      = "2024-03-01"
accepted_sha  = "fedcba987654"

  [[contributor.signing_keys]]
  format      = "gpg"
  fingerprint = "1234 5678 9ABC DEF0 1234  5678 9ABC DEF0 CAFE BABE"
  pubkey      = """
-----BEGIN PGP PUBLIC KEY BLOCK-----
[ASCII-armored key here]
-----END PGP PUBLIC KEY BLOCK-----
"""
```

---

## Appendix C: Verification Cheat Sheet

**Verify a single commit:**
```bash
git verify-commit <sha>
git verify-commit --verbose <sha>
```

**Show signatures in log:**
```bash
git log --show-signature
git log --pretty="%h %G? %GS %s"
# %G? codes: G=good, B=bad, U=unknown, N=no signature
```

**Check the Contributor Registry:**
```bash
# Extract signer fingerprint from a commit and check CONTRIBUTORS.iprl
git log --pretty="%H %GF" | head -20
```

**Verify the License signature:**
```bash
gpg --verify LICENSE.md.asc LICENSE.md
```

**Find Alien Changesets (unsigned commits) in a range:**
```bash
git log --pretty="%H %G?" main | awk '$2 == "N" || $2 == "B" {print $1}'
```

**Configure automatic commit signing (GPG):**
```bash
git config --global user.signingkey <KEY-FINGERPRINT>
git config --global commit.gpgsign true
```

**Configure automatic commit signing (SSH):**
```bash
git config --global gpg.format ssh
git config --global user.signingkey ~/.ssh/id_ed25519.pub
git config --global commit.gpgsign true
```

---

## Appendix D: Relationship to the Open Source Definition

The Open Source Initiative (OSI) Open Source Definition (OSD) requires, among other
criteria, that a license permit modification and the creation of derivative works
(OSD criterion 3) and not restrict use in any field of endeavor (OSD criterion 6).

**This License intentionally does not comply with OSD criteria 3 and 6** because:

- The prohibition on modification (Section 7(a)) is essential to preserve the
  Software's status as a defined, attributable IP asset. Modification rights, if
  granted universally, would make it impossible to maintain the Software as a bounded
  object of IP for registration and valuation purposes.

- The prohibition on commercial use (Section 7(b)) is essential to preserve the
  exclusive commercial value of the Software for the Licensed Contributors, which is
  the foundation of its use as a founder's contribution.

These restrictions are, however, **time-limited**: upon Dormancy (Section 10), the
Software automatically becomes governed by the Apache License, Version 2.0, which is
fully OSI-certified. IPRL is therefore best characterized as a **pre-open-source
source-available license with a built-in open source transition**.

Comparable licenses using similar time-limited or field-restricted structures include:
the Business Source License (BSL 1.1), the Server Side Public License (SSPL), the
Commons Clause addendum, and various "Functional Source Licenses." None of these are
OSI-approved, as is consistent with the structure of IPRL.

If OSI compliance from day one is required for a particular use case, the parties should
negotiate a separate license with the Licensed Contributors or await Dormancy.

---

*End of Intellectual Property Reserve License, Version 2.0*
