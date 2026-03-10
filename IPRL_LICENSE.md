# Intellectual Property Reserve License (IPRL)
**Version 2.0**

---

## Preamble

This License exists for a single primary purpose: to preserve the exclusive intellectual
property rights of its authors so that the Software may be used as a verifiable,
non-material asset — including as a founder's contribution when establishing a legal
entity, as an intangible asset in business valuation, or as registered IP in official
filings — while simultaneously making the source code publicly available for study,
execution, and commercial use in its unmodified form.

This License is a **modification-restricted source-available** license. It is
intentionally not an Open Source license under the Open Source Initiative (OSI)
definition because the prohibition on modification and derivative works (Section 7(a))
is essential to its IP-preservation purpose. Commercial use of the unmodified Software
is explicitly permitted. A time-triggered, irrevocable transition to a fully Open Source
license is provided in Section 10 (Dormancy and Fallback) to protect the public interest
in the event of development cessation. The relationship to the Open Source Definition is
explained in Appendix C.

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

**"Signing Key"** means any asymmetric cryptographic key pair or credential capable of
producing a verifiable digital signature on Changesets or files, where the public
portion or verifying credential is recorded in the Contributor Registry. This includes,
without limitation, OpenPGP/GPG keys, SSH keys, X.509 certificates, and any other
signing scheme supported by the VCS in use or by an applicable cryptographic standard
now existing or developed in the future. This License does not restrict the signing
algorithm, key type, or key size beyond the minimum required for cryptographic
verifiability against the recorded public credential.

**"Authoritative Changeset"** means a Changeset that is cryptographically signed by a
Licensed Contributor using a Signing Key registered in the Contributor Registry at the
time the Changeset is made, such that the signature can be verified using standard VCS
tooling (e.g., `git verify-commit`) against the public key recorded in the Contributor
Registry.

**"External Changeset"** means any Changeset that is not an Authoritative Changeset —
i.e., it is unsigned, or signed with a key not registered in the Contributor Registry.

**"Ratified Changeset"** means an External Changeset that has been explicitly accepted
into canonical history by an Authoritative Changeset in accordance with Section 5.

**"Contributor Registry"** means the authoritative, VCS-tracked list of Licensed
Contributors and their public signing credentials, maintained in a file named
`CONTRIBUTORS` in the root of the Software repository. The minimum required content
is defined in Appendix B; the file format is not mandated by this License.

**"Licensed Contributor"** means any natural person or legal entity whose Signing Key is
recorded in the current Contributor Registry at the time a relevant Changeset is made.

**"Founding Contributor"** means the first Licensed Contributor to apply this License
to the Software, whose identity is established by the Foundational Changeset described
in Section 3.1.

**"Contributor Pool"** means the set of all current Licensed Contributors.

**"Dormancy Period"** means a continuous period of twenty-four (24) calendar months
during which no Publication of the Software has been made by any Licensed Contributor
in any publicly accessible medium.

**"Fallback License"** means the Apache License, Version 2.0, as published by the Apache
Software Foundation (https://www.apache.org/licenses/LICENSE-2.0).

**"Publication"** means any act by a Licensed Contributor of making the Software, or any
portion thereof, publicly available in any medium, including but not limited to:
distribution of a source archive or compiled binary; publication of a versioned package
on a public registry; or, where the Software is managed in a Version Control System, the
making accessible of one or more new Changesets in a publicly accessible repository. A
formal versioned release is not required; any incremental addition to the publicly
accessible body of the Software constitutes a Publication.

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

### 3.1 Foundational Changeset

The Founding Contributor establishes this License by creating the **Foundational
Changeset**: an Authoritative Changeset that introduces, at minimum:

(a) A file `LICENSE.md` containing the full text of this License; and
(b) The initial `CONTRIBUTORS` file recording the Founding Contributor's entry.

Because the Foundational Changeset is itself cryptographically signed by the Founding
Contributor, the Changeset signature is the proof of authorship and the acceptance of
this License. A separate detached signature file (`LICENSE.md.asc`) is **optional**:
it may be included for the convenience of recipients who verify the License text outside
a VCS context, but its presence or absence does not affect the validity of this License.

The Founding Contributor's Signing Key must be capable of verification at the time of
the Foundational Changeset and for a reasonable period thereafter.

### 3.2 Changeset-Based Attribution (VCS Mode)

When the Software is managed in a VCS, a Licensed Contributor's authorship of any
content is established by the existence of one or more Authoritative Changesets
introducing or modifying that content. The Authoritative Changeset signature is the
cryptographic proof of authorship and the operative license declaration for that content.

**Per-file license headers are required** in all source files, but in VCS Mode the
header serves as a human-readable notice only — it does not need to embed the
contributor's public key or signing credential, because that information is recorded
in the `CONTRIBUTORS` file within the VCS history. The required header format is
defined in Appendix A.

To configure git commit signing for use with this License:

```
git config user.signingkey <KEY-ID-OR-PATH>
git config commit.gpgsign true
```

Signatures are verifiable using `git verify-commit <sha>` or `git log --show-signature`.

### 3.3 Snapshot / Out-of-VCS Distribution Mode

When the Software is distributed outside a VCS — for example, as a source archive,
a tarball, a file copy, or any form in which the full commit history and signatures
are not preserved — each distributed source file **must** include a file header
containing, in addition to the standard notice:

(a) the public signing credential (e.g., GPG public key, SSH public key, or certificate)
    of the Licensed Contributor responsible for that file's content; or
(b) a reference sufficient to locate and verify that credential independently (e.g., a
    key fingerprint and a durable URL or key server reference).

This ensures that recipients without VCS access can independently verify the authorship
chain. The full header format for Snapshot Mode is defined in Appendix A.

### 3.4 Signing Key Integrity and Compromise

The use of a cryptographic Signing Key does not limit a Licensed Contributor's ability
to assert exclusive rights by other legally accepted means. In the event of key loss,
revocation, or compromise:

(a) The Licensed Contributor should create a new Authoritative Changeset with a new
    Signing Key updating their entry in `CONTRIBUTORS`, signed (if possible) with the
    old key or countersigned by another Licensed Contributor;
(b) Authorship of prior Authoritative Changesets remains valid and provable by the
    immutable VCS history and the content of those Changesets;
(c) A statutory declaration or other legally sufficient evidence of identity may be
    used to supplement cryptographic evidence in legal proceedings.

---

## 4. The Contributor Pool

### 4.1 Formation

The Founding Contributor constitutes the initial Contributor Pool. The `CONTRIBUTORS`
file is the sole authoritative source for Pool membership and must contain, for each
Licensed Contributor, the information specified in Appendix B.

### 4.2 Admission of New Contributors

A person or entity is admitted to the Contributor Pool only when **both** of the
following conditions are satisfied:

(a) **Nomination**: An existing Licensed Contributor creates an Authoritative Changeset
    that adds the nominee's entry (including their Signing Key) to `CONTRIBUTORS`; and

(b) **Acceptance**: The nominee, using their own Signing Key (which must now match the
    key recorded under their entry), creates a subsequent Authoritative Changeset that
    contains an explicit written acceptance of the terms of this License.

An entry in `CONTRIBUTORS` without a corresponding acceptance Changeset from the
nominee does not constitute admission. A nominee's acceptance Changeset simultaneously
constitutes their grant under Section 4.4.

### 4.3 Platform-Independent Registry

The `CONTRIBUTORS` file is the sole mechanism for defining the Contributor Pool.
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
explicitly declaring their withdrawal and updating `CONTRIBUTORS`. Withdrawal:

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

## 5. External Changesets

### 5.1 Effect on Authorship

An External Changeset does not grant any intellectual property rights to its author under
this License. The author of an External Changeset:

(a) does not become a Licensed Contributor;
(b) does not acquire any rights to the Software beyond those granted to Users under
    Section 6; and
(c) has no effect on the IP ownership claims of any Licensed Contributor.

### 5.2 Ratification

An External Changeset is Ratified — and thereby incorporated into the canonical Software
history without constituting a license breach — when a Licensed Contributor creates an
Authoritative Changeset that:

(a) **Is a direct successor**: the Authoritative Changeset's parent (in VCS graph terms)
    is the External Changeset or an unbroken chain of External Changesets; or

(b) **Contains an explicit reference**: the Authoritative Changeset explicitly identifies
    the External Changeset by its cryptographic identifier (e.g., git commit SHA) and
    includes a statement of acceptance (e.g., "Ratified: <sha>").

A Ratifying Licensed Contributor assumes responsibility for the content of the Ratified
Changesets as part of the canonical Software history. The External Changeset author acquires
no additional rights through Ratification.

### 5.3 Rationale

The Ratification mechanism allows external contributions (e.g., bug reports with patches,
community pull requests) to be accepted without requiring contributors to formally join
the Pool, while ensuring that a Licensed Contributor vouches for each such contribution
and the authorship record of the Software remains unambiguous.

---

## 6. Rights Granted to Users

Subject to all conditions and restrictions of this License, the Licensed Contributors
collectively grant to You a worldwide, royalty-free, non-exclusive, non-transferable,
non-sublicensable, irrevocable (except as provided in Section 9) license to:

(a) **Read and Study**: access, read, copy, and analyze the source code for any purpose,
    commercial or non-commercial;

(b) **Compile and Execute**: compile the Software from source and execute or run the
    resulting binary or interpreted program for any purpose, commercial or non-commercial;

(c) **Redistribute Unmodified**: distribute verbatim, unmodified copies of the Software
    in source or compiled form for any purpose, commercial or non-commercial, provided
    that all of the following conditions are met:

    (i)   where distributed via a Version Control System: the complete record of
          Authoritative Changesets, including all cryptographic signatures, is preserved
          intact and independently verifiable; where distributed outside a VCS (e.g., as
          a source archive or binary), the requirements of Section 3.3 are satisfied;
    (ii)  all per-file license headers are preserved intact and unmodified;
    (iii) `LICENSE.md` and `CONTRIBUTORS` are included and unmodified, and
          `LICENSE.md.asc` is included unmodified if present;
    (iv)  the recipient is notified that the Software is governed by this License; and
    (v)   no additional restrictions are imposed on recipients beyond those stated here.

**This License does not grant any right to modify, adapt, translate, or create derivative
works of the Software.**

---

## 7. Restrictions

You are expressly prohibited from:

(a) **Modification**: modifying, adapting, translating, reverse-engineering for the purpose
    of creating competitive derivative works, or creating derivative works of the Software
    in any form;

(b) **Transfer of Rights**: sublicensing, selling, renting, leasing, or otherwise
    transferring Your rights in the Software to any third party;

(c) **Tampering with Attribution**: removing, obscuring, forging, or altering any license
    headers, Signing Key data, Authoritative Changeset signatures, `CONTRIBUTORS`,
    `LICENSE.md`, or `LICENSE.md.asc` (if present);

(d) **False Ownership Claims**: using the Software in any manner that could be construed
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
    updating `CONTRIBUTORS` to record the legal entity as successor-in-interest
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

### 10.1 Dormancy

The Software is **Dormant** when either of the following conditions is satisfied:

(a) **Apparent Dormancy**: no Publication of the Software has been made by any Licensed
    Contributor for a continuous period of twenty-four (24) calendar months, measured
    from the date of the last known Publication. Apparent Dormancy is a rebuttable
    presumption.

(b) **Voluntary Dormancy**: all Licensed Contributors listed in the then-current
    `CONTRIBUTORS` have each published a signed public statement explicitly declaring
    the Software Dormant and consenting to re-licensing under the Fallback License.
    Voluntary Dormancy is effective upon the last such declaration and is irrevocable.

### 10.2 Dormancy Claim and Diligent Search

Any person (a "Claimant") who wishes to invoke the Fallback License on grounds of
Apparent Dormancy must first publish a timestamped public notice (a "Dormancy Claim")
identifying the Software and stating the grounds. Before publishing, the Claimant must
conduct a **diligent search** in good faith — as that standard is generally understood
in copyright law and applied by courts of competent jurisdiction — to determine whether
any Licensed Contributor has made a recent Publication or is continuing active
development. The search must encompass reasonably accessible public registries, software
repositories, and the contact addresses for contributors recorded in `CONTRIBUTORS`.

The Claimant must wait **sixty (60) calendar days** after publishing the Dormancy Claim
before exercising any right under the Fallback License (the "Response Period").

Any Licensed Contributor may rebut Apparent Dormancy during the Response Period by
publishing a signed public statement that: (i) identifies a publicly accessible location
at which a new Publication of the Software is available or will be made within sixty
(60) days, or credibly states intent to resume development; and (ii) explicitly
references the Dormancy Claim. A valid rebuttal invalidates the Dormancy Claim and
resets the twenty-four-month period from the date of rebuttal.

If no valid rebuttal is received within the Response Period, Dormancy is Confirmed. A
Claimant who completes this procedure in good faith is granted a safe harbor against
infringement claims by Licensed Contributors arising from good-faith reliance on
Confirmed Dormancy.

### 10.3 Fallback License

Upon Confirmed or Voluntary Dormancy, the Software is irrevocably made available, in
addition to the rights already granted under this License, under the **Apache License,
Version 2.0** (https://www.apache.org/licenses/LICENSE-2.0). Licensed Contributors
retain copyright ownership of their respective contributions; the Fallback License is a
license, not a transfer of ownership. Confirmed Dormancy is irrevocable: subsequent
resumption of development does not withdraw the Fallback License from any person who
relied on it in good faith. The Apache License attribution requirements apply;
downstream recipients must preserve copyright notices and `CONTRIBUTORS`.

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

A cryptographic signature on a Changeset, or on the optional `LICENSE.md.asc` detached
signature file, is legally equivalent to a handwritten signature on a document asserting
authorship and acceptance of these terms.

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

The text of this License (`LICENSE.md`), the `CONTRIBUTORS` format guidance
(Appendix B), and all accompanying templates and documentation are released under the
**Creative Commons Zero v1.0 Universal (CC0)** license. You are free to copy, modify,
distribute, and use them without restriction, for any purpose, without asking permission.

---

## Appendix A: File Header Format

Every source file distributed under this License must carry a license header using
language-appropriate comment syntax. Two forms are defined:

### A.1 VCS Mode Header (minimum required in repositories with full commit history)

The VCS Mode header is a human-readable notice. The cryptographic proof of authorship
is in the Authoritative Changeset signature; the header does not need to embed key
material.

```
// [Optional copyright notice, e.g.: Copyright (C) 2024 Alice Smith]
// Distributed under the Intellectual Property Reserve License (IPRL) v2.0
// Licensed Contributors: see CONTRIBUTORS
```

### A.2 Snapshot Mode Header (required when distributed outside VCS context)

When files are distributed without full VCS history — e.g., as a source archive, a
tarball, or an individual file copy — the header must additionally include the public
signing credential of the contributing author, or a durable reference to it, so that
recipients can verify authorship without VCS access.

```
// [Optional copyright notice, e.g.: Copyright (C) 2024 Alice Smith]
// Distributed under the Intellectual Property Reserve License (IPRL) v2.0
// Licensed Contributors: see CONTRIBUTORS
//
// Author signing credential (for verification outside VCS):
// [include any of the following sufficient for independent verification:]
//   Key fingerprint: ABCD 1234 5678 9ABC DEF0  1234 5678 9ABC DEAD BEEF
//   SSH public key:  ssh-ed25519 AAAA...
//   Full public key block: -----BEGIN PGP PUBLIC KEY BLOCK----- ...
//   Key reference:   https://keyserver.example.com/pks/lookup?...
```

Any credential type that can be used to verify a Signing Key recorded in `CONTRIBUTORS`
is acceptable. The format is not mandated beyond the requirement of being sufficient for
independent verification.

---

## Appendix B: CONTRIBUTORS File

The `CONTRIBUTORS` file is the Contributor Registry defined in Section 1. It must be
maintained as an Authoritative Changeset — any modification must be in a Changeset
signed by a Licensed Contributor. The file is authenticated by the VCS signature of
the Changeset that introduces or modifies it; no separate signature file is required.

**Structure:** The file opens with the standard IPRL license header (same form as
Appendix A.1), followed by one entry per Licensed Contributor.

**Each entry consists of:**
1. Zero or more lines of optional, free-form identification information — any
   human-readable text the contributor chooses, such as a real name, pseudonym,
   email address, or any other data (including opaque identifiers like hashes)
   that the contributor may later use to prove their real-world identity;
2. The contributor's public signing credential in its native format.

**The public signing credential is the only mandatory element per entry.** All
identification text is voluntary. The file imposes no schema, field names, or
ordering beyond this.

Inline comment markers (`#`) may be used to distinguish identification text from key
material, but any plain-text layout that makes the association between identification
and key unambiguous is acceptable. Public keys for single-line schemes (e.g., SSH) may
appear one per line. Block-format keys (e.g., OpenPGP) span multiple lines in their
native armored format.

Example:

```
# Distributed under the Intellectual Property Reserve License (IPRL) v2.0
# Licensed Contributors:

# Alice Smith <alice@example.com>
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAI...

# Bob Jones  bob@work.example.com
-----BEGIN PGP PUBLIC KEY BLOCK-----
[key data]
-----END PGP PUBLIC KEY BLOCK-----

# pseudonym: ghost  sha256:e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855
ssh-ed25519 AAAAC3Nza...

# (key only, no identification — the contributor's identity is their key)
ssh-ed25519 AAAAC3Nzb...
```

---

## Appendix C: Relationship to the Open Source Definition

The Open Source Initiative (OSI) Open Source Definition (OSD) requires, among other
criteria, that a license permit modification and the creation of derivative works
(OSD criterion 3).

**This License intentionally does not comply with OSD criterion 3** (modification and
derivative works), for the following reason:

- The prohibition on modification (Section 7(a)) is essential to preserve the
  Software's status as a defined, attributable IP asset. If modification rights were
  granted universally, the Software could not be maintained as a bounded, identifiable
  object of IP for registration, valuation, and founder-contribution purposes.

This single-criterion non-compliance is structurally analogous to the Creative Commons
Attribution-NoDerivatives (CC BY-ND) family of licenses applied to software — freely
usable and commercially deployable without restriction, but not modifiable by those
outside the Contributor Pool. Upon Dormancy (Section 10), the Software automatically
becomes governed by the Apache License, Version 2.0, which is fully OSI-certified.
IPRL is therefore best characterized as a **no-derivatives source-available license
with a built-in open source transition**.

If OSI compliance from day one is required for a particular use case, the parties should
negotiate a separate license with the Licensed Contributors or await Dormancy.

---

*End of Intellectual Property Reserve License, Version 2.0*
