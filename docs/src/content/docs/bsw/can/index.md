---
title: "CAN Driver"
description: "Can: CAN driver (MCAN on RH850): frame transmission/reception, interrupts, baud-rate and controller state handling."
---


import { Badge } from '@astrojs/starlight/components';

# CAN Driver

Repo directory: `Can/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

CAN driver (MCAN on RH850): frame transmission/reception, interrupts, baud-rate and controller state handling.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `Can/src/Can.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (2 entries): `Can.c`, `Can_Irq.c`
- `include/` (2 entries): `Can.h`, `Can_Local.h`
- `autosar/` (1 entries): `Can_Rh850Mcan_bswmd.arxml`
- `make/` (4 entries): `Can_cfg.mak`, `Can_check.mak`, `Can_defs.mak`, `Can_rules.mak`
- `tools/` (4 entries): `Can.gpj`, `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`
- `doc/` (2 entries): `Can Peer Review Checklists.xlsm`, `TechnicalReference_Asr_Can_RH850_MCAN.pdf`

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

- [TechnicalReference_Asr_Can_RH850_MCAN.pdf](./technicalreference-asr-can-rh850-mcan/)

## Repository location

Repo path: `Can/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
