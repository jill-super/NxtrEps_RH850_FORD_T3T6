---
title: "Communication"
description: "Com: AUTOSAR COM: signal/PDU packing, routing, notifications and gatewaying between RTE and PduR."
---


import { Badge } from '@astrojs/starlight/components';

# Communication

Repo directory: `Com/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

AUTOSAR COM: signal/PDU packing, routing, notifications and gatewaying between RTE and PduR.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `Com/src/Com.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `Com.c`
- `include/` (1 entries): `Com.h`
- `autosar/` (3 entries): `Com_bswmd.arxml`, `Ford`, `GM`
- `make/` (4 entries): `Com_cfg.mak`, `Com_check.mak`, `Com_defs.mak`, `Com_rules.mak`
- `tools/` (4 entries): `Com.gpj`, `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`
- `doc/` (2 entries): `Com Peer Review Checklists.xlsm`, `TechnicalReference_Com.pdf`

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

- [TechnicalReference_Com.pdf](./technicalreference-com/)

## Repository location

Repo path: `Com/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
