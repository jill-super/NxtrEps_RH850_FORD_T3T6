---
title: "NVRAM Manager"
description: "NvM: NVRAM Manager: block-based persistent data with redundancy, CRC and callback handling over MemIf/Fee."
---


import { Badge } from '@astrojs/starlight/components';

# NVRAM Manager

Repo directory: `NvM/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

NVRAM Manager: block-based persistent data with redundancy, CRC and callback handling over MemIf/Fee.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `NvM/src/NvM.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (6 entries): `NvM.c`, `NvM_Act.c`, `NvM_Crc.c`, `NvM_JobProc.c`, `NvM_Qry.c`, `NvM_Queue.c`
- `include/` (8 entries): `NvM.h`, `NvM_Act.h`, `NvM_Cbk.h`, `NvM_Crc.h`, `NvM_JobProc.h`, `NvM_Qry.h`, `NvM_Queue.h`, `NvM_Types.h`
- `autosar/` (2 entries): `GM`, `NvM_bswmd.arxml`
- `make/` (4 entries): `NvM_cfg.mak`, `NvM_check.mak`, `NvM_defs.mak`, `NvM_rules.mak`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`, `NvM.gpj`
- `doc/` (2 entries): `NvM Peer Review Checklists.xlsm`, `TechnicalReference_NvM.pdf`

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

- [TechnicalReference_NvM.pdf](./technicalreference-nvm/)

## Repository location

Repo path: `NvM/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
