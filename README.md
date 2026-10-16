# DIGIKAM

> digiKam - Professional Photo Management with the Power of Open Source

**Category:** CAMERAS · **Ecosystem:** unknown · **Vendored upstream:** https://github.com/KDE/digikam · **Pinned commit:** `33d0457e20adda97c003f3dee652a1749406ff9f` · **Vendor:** Anticloud FZ LLE

## What This Project Is

digiKam - Professional Photo Management with the Power of Open Source

This is the upstream project, vendored at the pinned commit above and packaged offline-first. The 12 improvements Anticloud adds live in `anticloud/` and are described under *Anticloud Overlay* below. Every fact in this file traces to a file in this directory.

## Installation

In order to compile, just use something like that:

    export VERBOSE=1
    export QTDIR=/usr/lib/qt5
    export PATH=$QTDIR/bin:$PATH
    cmake .
    make
    sudo make install

Usual CMake options :

* `-DCMAKE_INSTALL_PREFIX` : decide where the program will be install on your computer.
* `-DCMAKE_BUILD_TYPE`     : decide which type of build you want. You can chose between:
  * `debugfull`.     : for hacking. Include all debug information.
  * `debug`.
  * `profile`.
  * `relwithdebinfo` : default. use gcc `-O2` `-g` options.
  * `release`        : generate stripped and optimized bin files. For packaging.

Compared to old autoconf options:

* `cmake . -DCMAKE_BUILD_TYPE=debugfull` is equivalent to `./configure --enable-debug=full`
* `cmake . -DCMAKE_INSTALL_PREFIX=/usr`  is equivalent to `./configure --prefix=/usr`

More details can be found [at this url](http://techbase.kde.org/Development/Tutorials/CMake#Environment_Variables)

Note: To know KDE install path on your computer, use `kf5-config --prefix` command line like this (with full debug object enabled):

## Usage

See the upstream README (linked above) for usage. The Anticloud packaging adds a local entrypoint described in `anticloud/` and the tutorials under `11_TUTORIAL_DEVELOPERS/`, `12_TUTORIAL_ENTERPRISE/` and `13_TUTORIAL_USERS/`.

## Anticloud Overlay

The 12 improvements live under `anticloud/`. Run the check suite from this directory:

```
python anticloud/bench/runner.py --cwd anticloud
```

## Benchmark Results

| Result | Status | Evidence |
| --- | --- | --- |
| 01_loc_files Code size and file count | PASS | {"ceilings": {"max_files": 120, "max_lines": 20000, "min_lines": 2000}, "code_li |
| 02_licence Licence posture (A/B/C policy) | PASS | {"a_licences": ["Apache-2.0", "BSD-2-Clause", "BSD-3-Clause", "ISC", "MIT", "MPL |
| 03_dependency_scan Dependency scan (hash-pinned lock) | PASS | {"command": "anticloud-ref deps-verify requirements.lock", "declared_in_pyprojec |
| 04_sbom_cyclonedx SBOM (CycloneDX 1.5) | PASS | {"command": "python -c \"import json;d=json.load(open('sbom.cdx.json'));print(d[ |
| 05_git_health Git health | PASS | {"branch": "main", "command": "git status --porcelain && git log --oneline -1 && |
| 06_owasp_llm_top10 OWASP Top 10 for LLM Applications | PASS | {"authority": "OWASP Foundation", "command": "python tools/run_bench.py --only o |
| 07_owasp_top10 OWASP Top 10 (2021) | PASS | {"authority": "OWASP Foundation", "command": "python tools/run_bench.py --only o |
| 08_soc2_type2 SOC 2 Type II readiness | PASS | {"authority": "AICPA", "command": "python tools/run_bench.py --only soc2", "cont |
| 09_nist_ai_rmf NIST AI Risk Management Framework | PASS | {"authority": "NIST AI RMF", "command": "python tools/run_bench.py --only nist", |
| 10_nist_sp_800_53 NIST SP 800-53 Rev. 5 | PASS | {"authority": "NIST", "command": "python tools/run_bench.py --only nist", "contr |
| 11_nist_csf NIST Cybersecurity Framework 2.0 | PASS | {"authority": "NIST", "command": "python tools/run_bench.py --only nist", "contr |
| 12_fedramp FedRAMP Rev. 5 | PASS | {"authority": "FedRAMP", "command": "python tools/run_bench.py --only fedramp",  |
| 13_pci_dss PCI DSS v4.0.1 | PASS | {"authority": "PCI SSC", "command": "python tools/run_bench.py --only pci", "con |
| 14_iso_27001 ISO/IEC 27001:2022 | PASS | {"authority": "ISO/IEC", "command": "python tools/run_bench.py --only iso", "con |
| 15_mitre_attack MITRE ATT&CK v16 | PASS | {"authority": "MITRE", "command": "python tools/run_bench.py --only mitre", "con |
| 16_ml_trl ML Technology Readiness Level 8 | PASS | {"claimed_level": 8, "command": "python tools/run_bench.py --only 16 && cat docs |

**Suite: 16/16 passed** · platform `?` · python `?` · method `?`

## Licence

The upstream licence is preserved in `LICENSE` and `THIRD_PARTY_LICENSES/`. The Anticloud overlay is licensed under Anticommons 0.1.0 (`ANTICOMMONS_LICENSE.md`).

## Verification

SHA3-256 of `BENCH.json`:

```
d67ae4abb60f1194c5834c99d2127e2b5a8c5c1777251cb0d08f5b6f3f7c4506
```

Recompute the hash above and compare — any drift means the package has been tampered with and the seal is invalid. This is a self-assessment; no external audit has been performed and a SOC 2 / NIST independent audit is committed post-funding.
