---
title: "Diagnostic Event Manager"
description: "Dem: Diagnostic Event Manager: DTC storage, debouncing, freeze frames and status per ISO 14229/15031."
---


import { Badge } from '@astrojs/starlight/components';

# Diagnostic Event Manager

Repo directory: `Dem/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

Diagnostic Event Manager: DTC storage, debouncing, freeze frames and status per ISO 14229/15031.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `Dem/src/Dem.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `Dem.c`
- `include/` (10 entries): `Dem.h`, `Dem_Cbk.h`, `Dem_Cdd_Types.h`, `Dem_Cfg_Declarations.h`, `Dem_Cfg_Definitions.h`, `Dem_Cfg_Macros.h`, `Dem_Cfg_Types.h`, `Dem_Dcm.h`, `Dem_Types.h`, `Dem_Validation.h`
- `autosar/` (3 entries): `Dem_Pre.arxml`, `Dem_bswmd.arxml`, `Dem_preo.arxml`
- `make/` (4 entries): `Dem_cfg.mak`, `Dem_check.mak`, `Dem_defs.mak`, `Dem_rules.mak`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Dem.gpj`, `Integrate.bat`, `IntegrationCopy`
- `doc/` (2 entries): `Dem Peer Review Checklists.xlsm`, `TechnicalReference_Dem.pdf`

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

- [TechnicalReference_Dem.pdf](./technicalreference-dem/)

## Repository location

Repo path: `Dem/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
