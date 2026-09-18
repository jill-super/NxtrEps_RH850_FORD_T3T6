---
title: "CAN XCP Transport"
description: "CanXcp: CAN transport layer for XCP measurement/calibration (DAQ/STIM over CAN)."
---


import { Badge } from '@astrojs/starlight/components';

# CAN XCP Transport

Repo directory: `CanXcp/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

CAN transport layer for XCP measurement/calibration (DAQ/STIM over CAN).

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `CanXcp/src/CanXcp.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `CanXcp.c`
- `include/` (2 entries): `CanXcp.h`, `CanXcp_Types.h`
- `make/` (4 entries): `CanXcp_cfg.mak`, `CanXcp_check.mak`, `CanXcp_defs.mak`, `CanXcp_rules.mak`
- `tools/` (2 entries): `CanXcp.gpj`, `CreateGHSProject.bat`
- `doc/` (2 entries): `CanXcp Peer Review Checklists.xlsm`, `TechnicalReference_CanXcp.pdf`

## Generated code and configuration

- No generator/contract folders observed.

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

- [TechnicalReference_CanXcp.pdf](./technicalreference-canxcp/)

## Repository location

Repo path: `CanXcp/` — subfolders present: `src/`, `include/`, `doc/`, `tools/`, `make/`.
