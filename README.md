# 🦉 OCapAudit

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OForensics-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OCapAudit** — Linux File Capabilities & SetUID Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OCapAudit is a Linux file-capabilities and SetUID/SetGID auditor that works both live and offline against a mounted image, chroot or disk via --root. It reads the security.capability xattr natively with a hand-written decoder for VFS cap v1/v2/v3 and enumerates setuid binaries, applying rules for dangerous capabilities on writable binaries, GTFOBins-style risks and missing nosuid mounts. It is strictly read-only — remediation commands are only printed, never executed — and maps findings to CWE and MITRE ATT&CK T1548.

---

## ✨ Features

- Live and offline (--root image/chroot) capability and setuid/setgid scanning
- Native security.capability xattr reader decoding VFS cap v1/v2/v3
- getcap -r output parsing plus optional getcap fallback
- Rules for dangerous caps on writable binaries, setuid scripts and GTFOBins risks
- fstab/mountinfo nosuid analysis and live process ambient/inheritable cap audit
- Baseline snapshots with drift diff and export TXT/MD/JSON/CSV/SARIF

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OCapAudit --scan
./OCapAudit --root /mnt/image --scan --format json -o report.json --fail-on high
./OCapAudit --caps-only --path /usr/bin
./OCapAudit --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OCapAudit --help   # watch every network call
firejail --net=none ./OCapAudit --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
