---
title: "Data dictionary toolchain (TL117A)"
description: "TL117A_DataDict: MATLAB `.m` databooks under each SW-C plus merge outputs in the integration tree."
---


import { Badge } from '@astrojs/starlight/components';

# Data dictionary toolchain (TL117A)

Repo directory: `TL117A_DataDict/` · Layer: `tools`

<Badge text="Host tool · third-party" variant="default" />

## Purpose and responsibility

MATLAB `.m` databooks under each SW-C plus merge outputs in the integration tree.

## Origin

**Host tool · third-party.** Host-side tooling (third-party / project tooling); no target ECU code.

:::note[Build-time artefact]
Not target ECU functionality: tooling or aggregated integration data. :::

## Key files

- `tools/` (2 entries): `DataDictionary.exe`, `Overrides_Template.xlsm`
- `doc/` (1 entries): `DataDict Peer Review Checklists.xlsm`

## Generated code and configuration

- No generator/contract folders observed.

## Public API

No runtime public API (tooling/integration data).

## Usage example

N/A — see the integration and build-system pages for how this artefact is used.

## Dependencies

- See the build-system and integration pages.

## Converted documentation

- No `.doc`/`.docx`/`.pdf` (or `doc/`-level `.txt`) sources found in this module.

## Repository location

Repo path: `TL117A_DataDict/` — subfolders present: `doc/`, `tools/`.
