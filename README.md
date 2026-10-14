# COGAT

![license](https://img.shields.io/badge/license-MIT-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-psychology-lightgrey)

> Anticloud-hardened packaging of the upstream project `COGAT` in category **PSYCHOLOGY**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** PSYCHOLOGY · **Upstream:** https://github.com/CognitiveAtlas/cogat-python · **Upstream pin:** `fabc06a7979c1caf964e4f41f36c6e534437afe5` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

# Cogat-Docker
[![CircleCI](https://circleci.com/gh/poldracklab/cogat/tree/master.svg?style=svg)](https://circleci.com/gh/poldracklab/cogat/tree/master)

Django application and containers for Spark and Neo4j to serve the Cognitive Atlas and manage development.

## Caveats regarding the ASSERTS relationship and use of the Assertion node:

The ASSERTS relationship was created for the special situation where a task has no contrasts but still asserts a concept.

In the old database theories would refer to a relationship between a task, contrast, and concept. Neo4j can't make a relationship from a node to another relationship so a new node type was created so that theories could relate to these assertions. These types of assertion nodes are automatically generated for every group of task-contrast-concept applicable on import. Outside of that migration assertion nodes are only generated when a assertion relationship is added to a theory. The caveat being queries against assertion nodes do not necessarily cover all implied assertions. The correct way to figure all assertions is to look directly at the task - hascontrast -> contrast <- measuredby - concept relationships.

## Getting started

This project uses docker and docker-compose:

Docker:  [https://docs.docker.com/installation/](https://docs.docker.com/installation/)<br />
Docker Compose: [https://docs.docker.com/compose/install/](https://docs.docker.com/compose/install/)

Docker file for neo4j taken from [https://github.com/kbastani/docker-neo4j](https://github.com/kbastani/docker-neo4j) and modified to do some data imports.

## Create default user

Add `MAKE_DEFAULT_USER=True` to the `.env` file in the root of the project. The user specificed in scripts/create_superuser.py will then be created on startup of the uwsgi container.

## Old users

The import contianer looks for an environment variable named `MYSQL_DUMP` and uses its value as the sql dump file to import into mysql. This variable should be defined in `.env`. The users will be imported when the import container is started. It should be started with docker-compose using the `docker-compose-import.yml` config file.

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Unknown (no standard manifest detected)** (manifests: none detected; scanned in UPSTREAM_CLONE)
- Top-level source layout: `cognitive/`, `compose/`, `scripts/`
- Snapshot size: **213 files**, **24391 lines of code** (measured; see Benchmarks)
- Primary languages: `.html` (56), `.py` (46), `.png` (28), `.js` (24), `.css` (16), `(none)` (6)
- Upstream commit pinned for this packaging: `fabc06a7979c1caf964e4f41f36c6e534437afe5`

---

## Installation

This project uses docker and docker-compose:

Docker:  [https://docs.docker.com/installation/](https://docs.docker.com/installation/)<br />
Docker Compose: [https://docs.docker.com/compose/install/](https://docs.docker.com/compose/install/)

Docker file for neo4j taken from [https://github.com/kbastani/docker-neo4j](https://github.com/kbastani/docker-neo4j) and modified to do some data imports.

*Section quoted from the upstream readme.*
Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

The ASSERTS relationship was created for the special situation where a task has no contrasts but still asserts a concept.

In the old database theories would refer to a relationship between a task, contrast, and concept. Neo4j can't make a relationship from a node to another relationship so a new node type was created so that theories could relate to these assertions. These types of assertion nodes are automatically generated for every group of task-contrast-concept applicable on import. Outside of that migration assertion nodes are only generated when a assertion relationship is added to a theory. The caveat being queries against assertion nodes do not necessarily cover all implied assertions. The correct way to figure all assertions is to look directly at the task - hascontrast -> contrast <- measuredby - concept relationships.

*Section quoted from the upstream readme.*
Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

The upstream API surface is defined by the `COGAT` source tree vendored in `UPSTREAM_CLONE/` (Unknown (no standard manifest detected) ecosystem). Public entry points:

- Source modules: `cognitive/`, `compose/`, `scripts/`
- Overlay API: `anticloud/cli.py` exposes 13 subcommands with JSON stdout; `anticloud/bench/runner.py` runs the 16-check suite; `anticloud/provenance/chain.py` exposes the SHA3-256 + Ed25519 provenance chain.

---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Unknown (no standard manifest detected) |
| Manifests detected | none |
| Files in snapshot | 213 |
| Lines of code | 24391 |
| Dependency references | 0 |
| Upstream license | MIT |
| Overlay license | Anticommons 0.1.0 |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

No configuration section was found in the upstream readme. Configuration-relevant files detected in this project directory:

- None detected at the snapshot root; consult the upstream documentation link in the Upstream section.

Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

Upstream contributions: fork the `COGAT` project, create a feature branch, and open a pull request against upstream. Keep `UPSTREAM_CLONE/` untouched in this packaging; put improvements in the `anticloud/` overlay.

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: MIT** (evidence: `LICENSE` in the upstream snapshot).

License file excerpt:

```text
The MIT License (MIT)
Copyright (c) 2017 CognitiveAtlas

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original MIT terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `MIT` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `COGAT` (category: PSYCHOLOGY)
- **Upstream URL:** https://github.com/CognitiveAtlas/cogat-python
- **Pinned commit (SHA):** `fabc06a7979c1caf964e4f41f36c6e534437afe5`
- **Branch:** master
- **Pin provenance:** GitHub API commits/master. The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`ffdd2df17499c9179151dd0a9d8a232171a346671da7856982791903830142e2`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe and Mail, Business Insider, National Post, Financial Post, StreetInsider, Digital Journal, Barchart, International Business Times, and fox47 · National Law Review.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.

