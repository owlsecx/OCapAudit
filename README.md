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

Linux file capabilities & setuid/setgid auditor

---

## ✨ Features

- Offline (--root image / chroot / mounted disk) and live (/usr /bin /sbin /opt custom) tree scanning
- Native security.capability xattr reader with a hand-written decoder for VFS cap v1 / v2 / v3 (namespaced rootid) structures — no external libs
- `getcap -r` output parser (old "= cap+ep" and new "cap=ep" syntaxes) + optional getcap fallback
- SetUID / SetGID enumeration via lstat mode bits, ownership, hardlink, ELF / shebang classification
- Ruleset: dangerous caps on writable / user-owned binaries, setuid interpreters & scripts, caps in tmp / home paths, GTFOBins-style risky binaries, full-cap sets, inheritable caps, namespaced caps
- fstab / mountinfo analysis for missing nosuid
- Live process ambient / inheritable cap audit
- CWE + MITRE ATT&CK T1548 mapping, severity, printed-only remediation (setcap -r / chmod)
- Baseline snapshots + drift diff
- Exports TXT / Markdown / JSON / CSV / SARIF 2.1.0
- Full CLI with CI gates (--fail-on, --min-severity)
- --demo self-test with a synthetic temp tree

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OCapAudit
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
