---
title: "ECU Configuration"
description: "EcuC: ECU Configuration: no code of its own; the ECUC `.arxml` parameter set that configures every BSW module."
---


import { Badge } from '@astrojs/starlight/components';

# ECU Configuration

Repo directory: `EcuC/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

ECU Configuration: no code of its own; the ECUC `.arxml` parameter set that configures every BSW module.

## Origin

**Vector-provided · MICROSAR.** ECU configuration of the Vector MICROSAR stack (`.arxml` only; no compilable source in this folder).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `autosar/` (3 entries): `EcuC_bswmd.arxml`, `EcuC_preo_Rh850_GreenHills.arxml`, `Ford`
- `tools/` (2 entries): `Integrate.bat`, `IntegrationCopy`
- `doc/` (2 entries): `EcuC Baseline Naming Help.txt`, `EcuC Peer Review Checklists.xlsm`

## Generated code and configuration

- AUTOSAR model fragments: `autosar/` (`.arxml`/`.dpa`/`.dcf`).

## Public API

For Vector/Renesas drivers the API is the AUTOSAR-specified set declared in `include/` (e.g. `Init`, `GetVersionInfo`, job APIs) plus callbacks configured in ECUC; the exact set follows the Vector Technical Reference linked below.

## Usage example

```c
/* Typical BSW usage (see Technical Reference for exact API): */
/* EcuM initialises the stack; SW-Cs use services via the RTE. */
Std_ReturnType ret = EcuM_Init(); /* integration startup, simplified */
```

## Dependencies

- Configured through DaVinci/ECUC; initialised by EcuM in the integration startup order.
- Service users reach it via the RTE; error reporting via Det/Dem where applicable.

## Converted documentation

- [EcuC Baseline Naming Help.txt](./ecuc-baseline-naming-help/)

## Repository location

Repo path: `EcuC/` — subfolders present: `autosar/`, `doc/`, `tools/`.
