---
title: "CAN Interface"
description: "CanIf: CAN Interface: abstracts CAN controllers, routes PDUs between Can driver, CanTp/CanNm/XCP and PduR."
---


import { Badge } from '@astrojs/starlight/components';

# CAN Interface

Repo directory: `CanIf/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

CAN Interface: abstracts CAN controllers, routes PDUs between Can driver, CanTp/CanNm/XCP and PduR.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `CanIf/src/CanIf.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `CanIf.c`
- `include/` (5 entries): `CanIf.h`, `CanIf_Cbk.h`, `CanIf_GeneralTypes.h`, `CanIf_Hooks.h`, `CanIf_Types.h`
- `autosar/` (3 entries): `CanIf_bswmd.arxml`, `Ford`, `GM`
- `make/` (4 entries): `CanIf_cfg.mak`, `CanIf_check.mak`, `CanIf_defs.mak`, `CanIf_rules.mak`
- `tools/` (4 entries): `CanIf.gpj`, `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`
- `doc/` (2 entries): `CanIf Peer Review Checklists.xlsm`, `TechnicalReference_CanIf.pdf`

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

- [TechnicalReference_CanIf.pdf](./technicalreference-canif/)

## Repository location

Repo path: `CanIf/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
