---
title: "Diagnostic Communication Manager"
description: "Dcm: Diagnostic Communication Manager (UDS ISO 14229): sessions, services, DID/routine handling with Dem."
---


import { Badge } from '@astrojs/starlight/components';

# Diagnostic Communication Manager

Repo directory: `Dcm/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

Diagnostic Communication Manager (UDS ISO 14229): sessions, services, DID/routine handling with Dem.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `Dcm/src/Dcm.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (2 entries): `Dcm.c`, `Dcm_Ext.c`
- `include/` (12 entries): `Dcm.h`, `Dcm_Cbk.h`, `Dcm_Core.h`, `Dcm_CoreCbk.h`, `Dcm_CoreInt.h`, `Dcm_CoreTypes.h`, `Dcm_Ext.h`, `Dcm_ExtCbk.h`, `Dcm_ExtInt.h`, `Dcm_ExtTypes.h`, `Dcm_Int.h`, `Dcm_Types.h`
- `autosar/` (2 entries): `Dcm_bswmd.arxml`, `Dcm_preo.arxml`
- `make/` (4 entries): `Dcm_cfg.mak`, `Dcm_check.mak`, `Dcm_defs.mak`, `Dcm_rules.mak`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Dcm.gpj`, `Integrate.bat`, `IntegrationCopy`
- `doc/` (2 entries): `Dcm Peer Review Checklists.xlsm`, `TechnicalReference_Dcm.pdf`

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

- [TechnicalReference_Dcm.pdf](./technicalreference-dcm/)

## Repository location

Repo path: `Dcm/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
