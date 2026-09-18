---
title: "ECU State Manager"
description: "EcuM: ECU State Manager: startup/shutdown sequences, sleep/wakeup and driver initialisation order."
---


import { Badge } from '@astrojs/starlight/components';

# ECU State Manager

Repo directory: `EcuM/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

ECU State Manager: startup/shutdown sequences, sleep/wakeup and driver initialisation order.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `EcuM/src/EcuM.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `EcuM.c`
- `include/` (3 entries): `EcuM.h`, `EcuM_Cbk.h`, `EcuM_Error.h`
- `autosar/` (3 entries): `EcuM_bswmd.arxml`, `Ford`, `GM`
- `make/` (4 entries): `EcuM_cfg.mak`, `EcuM_check.mak`, `EcuM_defs.mak`, `EcuM_rules.mak`
- `tools/` (4 entries): `CreateGHSProject.bat`, `EcuM.gpj`, `Integrate.bat`, `IntegrationCopy`
- `doc/` (2 entries): `EcuM Peer Review Checklists.xlsm`, `TechnicalReference_EcuM.pdf`

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

- [TechnicalReference_EcuM.pdf](./technicalreference-ecum/)

## Repository location

Repo path: `EcuM/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
