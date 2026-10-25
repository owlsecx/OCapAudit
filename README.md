# 🦉 OCapAudit

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OForensics-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
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

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
