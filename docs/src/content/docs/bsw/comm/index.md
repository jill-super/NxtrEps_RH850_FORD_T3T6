---
title: "Communication Manager"
description: "ComM: Communication Manager: network resource coordination requested by users (e.g. DCM, NM)."
---


import { Badge } from '@astrojs/starlight/components';

# Communication Manager

Repo directory: `ComM/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

Communication Manager: network resource coordination requested by users (e.g. DCM, NM).

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `ComM/src/ComM.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `ComM.c`
- `include/` (6 entries): `ComM.h`, `ComM_BusSM.h`, `ComM_Dcm.h`, `ComM_EcuMBswM.h`, `ComM_Nm.h`, `ComM_Types.h`
- `autosar/` (3 entries): `ComM_bswmd.arxml`, `Ford`, `GM`
- `make/` (4 entries): `ComM_cfg.mak`, `ComM_check.mak`, `ComM_defs.mak`, `ComM_rules.mak`
- `tools/` (4 entries): `ComM.gpj`, `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`
- `doc/` (2 entries): `ComM Peer Review Checklists.xlsm`, `TechnicalReference_ComM.pdf`

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

- [TechnicalReference_ComM.pdf](./technicalreference-comm/)

## Repository location

Repo path: `ComM/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
