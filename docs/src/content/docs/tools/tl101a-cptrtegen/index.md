---
title: "Component RTE Generator (TL101A)"
description: "TL101A_CptRteGen: Generates per-SW-C RTE contracts/stubs from the DaVinci/ECUC model."
---


import { Badge } from '@astrojs/starlight/components';

# Component RTE Generator (TL101A)

Repo directory: `TL101A_CptRteGen/` · Layer: `tools`

<Badge text="Host tool · third-party" variant="default" />

## Purpose and responsibility

Generates per-SW-C RTE contracts/stubs from the DaVinci/ECUC model.

## Origin

**Host tool · third-party.** Host-side tooling (third-party / project tooling); no target ECU code.

:::note[Build-time artefact]
Not target ECU functionality: tooling or aggregated integration data. :::

## Key files

- `tools/` (2 entries): `InternalBehavior`, `Sip`
- `doc/` (2 entries): `CptRteGenNotes.txt`, `TL101A_CptRteGen Peer Review Checklists.xlsm`

## Generated code and configuration

- No generator/contract folders observed.

## Public API

No runtime public API (tooling/integration data).

## Usage example

N/A — see the integration and build-system pages for how this artefact is used.

## Dependencies

- See the build-system and integration pages.

## Converted documentation

- [CptRteGenNotes.txt](./cptrtegennotes/)

## Repository location

Repo path: `TL101A_CptRteGen/` — subfolders present: `doc/`, `tools/`.
