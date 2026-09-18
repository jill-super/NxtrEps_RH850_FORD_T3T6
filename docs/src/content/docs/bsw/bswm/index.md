---
title: "BSW Mode Manager"
description: "BswM: BSW Mode Manager: arbitrates vehicle/ECU modes and executes mode-dependent action lists (e.g. communication control, PDU groups)."
---


import { Badge } from '@astrojs/starlight/components';

# BSW Mode Manager

Repo directory: `BswM/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

BSW Mode Manager: arbitrates vehicle/ECU modes and executes mode-dependent action lists (e.g. communication control, PDU groups).

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `BswM/src/BswM.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `BswM.c`
- `include/` (17 entries): `BswM.h`, `BswM_CanSM.h`, `BswM_ComM.h`, `BswM_Dcm.h`, `BswM_EcuM.h`, `BswM_EthIf.h`, `BswM_EthSM.h`, `BswM_FrSM.h`, `BswM_J1939Dcm.h`, `BswM_J1939Nm.h`, `BswM_LinSM.h`, `BswM_LinTp.h`, `BswM_Nm.h`, `BswM_NvM.h` (+3 more)
- `autosar/` (3 entries): `BswM_bswmd.arxml`, `Ford`, `GM`
- `make/` (4 entries): `BswM_cfg.mak`, `BswM_check.mak`, `BswM_defs.mak`, `BswM_rules.mak`
- `tools/` (4 entries): `BswM.gpj`, `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`
- `doc/` (2 entries): `BswM Peer Review Checklists.xlsm`, `TechnicalReference_BswM.pdf`

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

- [TechnicalReference_BswM.pdf](./technicalreference-bswm/)

## Repository location

Repo path: `BswM/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
