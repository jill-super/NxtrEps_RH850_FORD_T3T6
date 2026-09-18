---
title: "CAN Network Management"
description: "CanNm: CAN Network Management: coordinated bus sleep/wakeup and node monitoring on the Ford Hi-Speed buses."
---


import { Badge } from '@astrojs/starlight/components';

# CAN Network Management

Repo directory: `CanNm/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

CAN Network Management: coordinated bus sleep/wakeup and node monitoring on the Ford Hi-Speed buses.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `CanNm/src/CanNm.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `CanNm.c`
- `include/` (2 entries): `CanNm.h`, `CanNm_Cbk.h`
- `autosar/` (3 entries): `CanNm_bswmd.arxml`, `Ford`, `GM`
- `make/` (4 entries): `CanNm_cfg.mak`, `CanNm_check.mak`, `CanNm_defs.mak`, `CanNm_rules.mak`
- `tools/` (4 entries): `CanNm.gpj`, `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`
- `doc/` (2 entries): `CanNm Peer Review Checklists.xlsm`, `TechnicalReference_CanNm.pdf`

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

- [TechnicalReference_CanNm.pdf](./technicalreference-cannm/)

## Repository location

Repo path: `CanNm/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
