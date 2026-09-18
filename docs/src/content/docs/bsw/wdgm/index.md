---
title: "Watchdog Manager"
description: "WdgM: Watchdog Manager: alive-supervision of tasks/SW-Cs with configurable supervision entities."
---


import { Badge } from '@astrojs/starlight/components';

# Watchdog Manager

Repo directory: `WdgM/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

Watchdog Manager: alive-supervision of tasks/SW-Cs with configurable supervision entities.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `WdgM/src/WdgM.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (2 entries): `WdgM.c`, `WdgM_Checkpoint.c`
- `include/` (2 entries): `WdgM.h`, `WdgM_Cfg.h`
- `autosar/` (2 entries): `GM`, `WdgM_bswmd.arxml`
- `make/` (4 entries): `WdgM_cfg.mak`, `WdgM_check.mak`, `WdgM_defs.mak`, `WdgM_rules.mak`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`, `WdgM.gpj`
- `doc/` (2 entries): `TechnicalReference_WdgM.pdf`, `WdgM Peer Review Checklists.xlsm`

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

- [TechnicalReference_WdgM.pdf](./technicalreference-wdgm/)

## Repository location

Repo path: `WdgM/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
