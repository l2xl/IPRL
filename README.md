# About Intellectual Property Reserve License

This repository is intended to publish a custom license called the **Intellectual Property Reserve License (IPRL)**.  
This license is designed for authors who intend to retain full intellectual property rights over their software while still allowing public use **for educational and non-modifying purposes**.

The goal of IPRL is to enable authors to publish their source code openly (e.g., on GitHub) and maintain exclusive ownership, so that this IP for example can later be contributed as a **founder’s capital contribution** when starting a company.

---

## Key Principles

- ✅ Free to **view, compile, and run** the code for non-commercial, educational, and non-modifying purposes.
- ❌ **Modifying** the source code in any way is prohibited.
- ❌ **Commercial redistribution or derivative works** are forbidden without explicit, separate agreement.
- ✅ All rights remain **exclusively with the original author**, with legal enforcement options for violations.

---

## Usage Instructions

To use this license for your own project, follow these steps:

### 1. Include Required Files

Add the following to your repository:

* LICENSE.md — the license text

* LICENSE.md.asc — your signed proof of authorship (see below)

### 2. Add License Header to Each Source File

Each source file must begin with a license header block containing:

```
[Optional copyright notice with author requisites]
Distributed under the Intellectual Property Reserve License
see the accompanying file LICENSE.md
GPG: [Your Public GPG Key Here]
```

You can include this block as a comment appropriate to your file's language (e.g., `#`, `//`, or `/* */`).

### 3. Generate LICENSE.md.asc

You must provide a signed statement confirming your authorship using GPG:

#### a. Generate a GPG key (if you don't already have one)

```bash
gpg --full-generate-key
```

Follow the prompts to set your name/email and create a passphrase.

#### b. Export your **public key** (to include in headers)

```bash
gpg --armor --export your@email.com > publickey.asc
```

#### c. Sign the LICENSE.md

```bash
gpg --clearsign LICENSE.md
```

---

## Relicensing Instructions (e.g., for Open Source Transition)

If the intellectual property is later transferred (e.g., to a company as founder’s capital), and a decision is made to relicense under an Open Source license, follow this process to avoid legal ambiguity:

1. Add a Clause in the License (Already Present)

The IPRL contains a clause allowing the original rights holder to relicense the software under other terms.

2. Create RELICENSING.md

Create a file documenting the change, for example:

```

# License Change Declaration

On 2025-08-01, the intellectual property previously licensed under the Intellectual Property Reserve License (IPRL) was officially re-licensed under the MIT License.

This decision was made by NewCo Ltd. as the exclusive rights holder of the software, in accordance with the original IPRL license.

Jane Founder  
CEO, NewCo Ltd.  

```

3. Sign the Declaration (Optional)

Digitally sign RELICENSING.md using:

```
gpg --clearsign RELICENSING.md
# Output: RELICENSING.md.asc

```

4. Commit the Change

Make a git commit including:

* New LICENSE file (e.g., MIT)

* RELICENSING.md

* new AUTHORITY.asc with signature of RELICENSING.md

---

## Legal Note

The text of the IPRL license and all accompanying instructions are released under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/).  
You are free to copy, adapt, and reuse them in your own projects without restriction.
