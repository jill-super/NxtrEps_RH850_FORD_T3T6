---
title: "CRC Library"
description: "Crc: CRC library: software checksums used by E2E protection and NvM/Com safety mechanisms."
---


import { Badge } from '@astrojs/starlight/components';

# CRC Library

Repo directory: `Crc/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

CRC library: software checksums used by E2E protection and NvM/Com safety mechanisms.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `Crc/src/Crc.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `Crc.c`
- `include/` (1 entries): `Crc.h`
- `autosar/` (1 entries): `Crc_bswmd.arxml`
- `make/` (4 entries): `Crc_cfg.mak`, `Crc_check.mak`, `Crc_defs.mak`, `Crc_rules.mak`
- `tools/` (4 entries): `Crc.gpj`, `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`
- `doc/` (2 entries): `Crc Peer Review Checklists.xlsm`, `TechnicalReference_Crc.pdf`

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

- [TechnicalReference_Crc.pdf](./technicalreference-crc/)

## Repository location

Repo path: `Crc/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
