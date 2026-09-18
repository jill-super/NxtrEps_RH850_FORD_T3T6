---
title: "CAN State Manager"
description: "CanSm: CAN State Manager: per-network communication-mode control (via ComM) and bus-off/error recovery."
---


import { Badge } from '@astrojs/starlight/components';

# CAN State Manager

Repo directory: `CanSm/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

CAN State Manager: per-network communication-mode control (via ComM) and bus-off/error recovery.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `CanSm/src/CanSM.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `CanSM.c`
- `include/` (8 entries): `CanSM.h`, `CanSM_BswM.h`, `CanSM_Cbk.h`, `CanSM_ComM.h`, `CanSM_Dcm.h`, `CanSM_EcuM.h`, `CanSM_Int.h`, `CanSM_TxTimeoutException.h`
- `autosar/` (3 entries): `CanSM_bswmd.arxml`, `Ford`, `GM`
- `make/` (4 entries): `CanSM_cfg.mak`, `CanSM_check.mak`, `CanSM_defs.mak`, `CanSM_rules.mak`
- `tools/` (4 entries): `CanSM.gpj`, `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`
- `doc/` (2 entries): `CanSm Peer Review Checklists.xlsm`, `TechnicalReference_CanSM.pdf`

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

- [TechnicalReference_CanSM.pdf](./technicalreference-cansm/)

## Repository location

Repo path: `CanSm/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
