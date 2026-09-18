---
title: "Watchdog Interface"
description: "WdgIf: Watchdog Interface: routes trigger/mode requests to the underlying watchdog driver."
---


import { Badge } from '@astrojs/starlight/components';

# Watchdog Interface

Repo directory: `WdgIf/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

Watchdog Interface: routes trigger/mode requests to the underlying watchdog driver.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `WdgIf/src/WdgIf.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `WdgIf.c`
- `include/` (3 entries): `WdgIf.h`, `WdgIf_Cfg.h`, `WdgIf_Types.h`
- `autosar/` (2 entries): `GM`, `WdgIf_bswmd.arxml`
- `make/` (4 entries): `WdgIf_cfg.mak`, `WdgIf_check.mak`, `WdgIf_defs.mak`, `WdgIf_rules.mak`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`, `WdgIf.gpj`
- `doc/` (2 entries): `TechnicalReference_WdgIf.pdf`, `WdgIf Peer Review Checklists.xlsm`

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

- [TechnicalReference_WdgIf.pdf](./technicalreference-wdgif/)

## Repository location

Repo path: `WdgIf/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
