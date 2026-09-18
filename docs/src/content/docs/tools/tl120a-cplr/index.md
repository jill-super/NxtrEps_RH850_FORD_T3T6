---
title: "Green Hills compiler toolchain (TL120A)"
description: "TL120A_Cplr: RH850/V850 cross-compiler, libraries, probes and target descriptions used to build the ECU image."
---


import { Badge } from '@astrojs/starlight/components';

# Green Hills compiler toolchain (TL120A)

Repo directory: `TL120A_Cplr/` · Layer: `tools`

<Badge text="Host tool · third-party" variant="default" />

## Purpose and responsibility

RH850/V850 cross-compiler, libraries, probes and target descriptions used to build the ECU image.

## Origin

**Host tool · third-party.** Host-side tooling (Green Hills Software (MULTI)); no target ECU code.

:::note[Build-time artefact]
Not target ECU functionality: tooling or aggregated integration data. :::

## Key files

- `tools/` (261 entries): `.about`, `.about_secondary`, `850eserv2.exe`, `850eserv2_server.exe`, `850win.exe`, `BfwE20RH850G3.s`, `BfwE20mini2_E121h.s`, `BfwE20mini2_V106.s`, `BfwE20mini2_V107.s`, `BfwE20mini2_V120.s`, `BfwE20mini2_V121.s`, `BfwE2RH850.s`, `Communi.dll`, `E2_RH850.bit` (+247 more)
- `doc/` (2 entries): `TL120A_Cplr Peer Review Checklist.xlsm`, `Version Notes.docx`

## Generated code and configuration

- No generator/contract folders observed.

## Public API

No runtime public API (tooling/integration data).

## Usage example

N/A — see the integration and build-system pages for how this artefact is used.

## Dependencies

- See the build-system and integration pages.

## Converted documentation

- [Version Notes.docx](./version-notes/)
- [build_v800.pdf](./build-v800/)
- [c_error_ref.pdf](./c-error-ref/)
- [connect_v800.pdf](./connect-v800/)
- [ghprobe.pdf](./ghprobe/)
- [ghprobe_v850.pdf](./ghprobe-v850/)
- [probe_release_notes.pdf](./probe-release-notes/)
- [probe_start.pdf](./probe-start/)
- [release_notes_v800.pdf](./release-notes-v800/)
- [supertrace_start.pdf](./supertrace-start/)
- [sv-rte-us-72.pdf](./sv-rte-us-72/)
- [sv-v850e2-us-910.pdf](./sv-v850e2-us-910/)
- [sv-v850e2-us-915.pdf](./sv-v850e2-us-915/)
- [threadx.pdf](./threadx/)

## Repository location

Repo path: `TL120A_Cplr/` — subfolders present: `doc/`, `tools/`.
