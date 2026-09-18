---
title: "CAN Transport Protocol"
description: "CanTp: CAN Transport Protocol (ISO 15765-2): segmentation/reassembly for UDS diagnostics over CAN."
---


import { Badge } from '@astrojs/starlight/components';

# CAN Transport Protocol

Repo directory: `CanTp/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

CAN Transport Protocol (ISO 15765-2): segmentation/reassembly for UDS diagnostics over CAN.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `CanTp/src/CanTp.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `CanTp.c`
- `include/` (4 entries): `CanTp.h`, `CanTp_Cbk.h`, `CanTp_Priv.h`, `CanTp_Types.h`
- `autosar/` (3 entries): `CanTp_bswmd.arxml`, `Ford`, `GM`
- `make/` (4 entries): `CanTp_cfg.mak`, `CanTp_check.mak`, `CanTp_defs.mak`, `CanTp_rules.mak`
- `tools/` (4 entries): `CanTp.gpj`, `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`
- `doc/` (2 entries): `CanTp Peer Review Checklists.xlsm`, `TechnicalReference_CanTp.pdf`

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

- [TechnicalReference_CanTp.pdf](./technicalreference-cantp/)

## Repository location

Repo path: `CanTp/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
