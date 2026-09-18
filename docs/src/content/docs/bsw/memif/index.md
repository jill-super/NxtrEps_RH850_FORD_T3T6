---
title: "Memory Abstraction Interface"
description: "MemIf: Memory Abstraction Interface: uniform API over Fee/EA for NvM blocks."
---


import { Badge } from '@astrojs/starlight/components';

# Memory Abstraction Interface

Repo directory: `MemIf/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

Memory Abstraction Interface: uniform API over Fee/EA for NvM blocks.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `MemIf/src/MemIf.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `MemIf.c`
- `include/` (2 entries): `MemIf.h`, `MemIf_Types.h`
- `autosar/` (1 entries): `MemIf_bswmd.arxml`
- `make/` (4 entries): `MemIf_cfg.mak`, `MemIf_check.mak`, `MemIf_defs.mak`, `MemIf_rules.mak`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`, `MemIf.gpj`
- `doc/` (2 entries): `MemIf Peer Review Checklists.xlsm`, `TechnicalReference_MemIf.pdf`

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

- [TechnicalReference_MemIf.pdf](./technicalreference-memif/)

## Repository location

Repo path: `MemIf/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
