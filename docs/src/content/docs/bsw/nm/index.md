---
title: "Network Management"
description: "Nm: Generic Network Management interface coordinating CanNm instances."
---


import { Badge } from '@astrojs/starlight/components';

# Network Management

Repo directory: `Nm/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

Generic Network Management interface coordinating CanNm instances.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `Nm/src/Nm.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `Nm.c`
- `include/` (3 entries): `Nm.h`, `NmStack_Types.h`, `Nm_Cbk.h`
- `autosar/` (3 entries): `Ford`, `GM`, `Nm_bswmd.arxml`
- `make/` (4 entries): `Nm_cfg.mak`, `Nm_check.mak`, `Nm_defs.mak`, `Nm_rules.mak`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`, `Nm.gpj`
- `doc/` (2 entries): `Nm Peer Review Checklists.xlsm`, `TechnicalReference_Nm.pdf`

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

- [TechnicalReference_Nm.pdf](./technicalreference-nm/)

## Repository location

Repo path: `Nm/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
