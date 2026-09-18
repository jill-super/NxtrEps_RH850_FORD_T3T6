---
title: "I/O Hardware Abstraction"
description: "IoHwAb: I/O Hardware Abstraction: project signal mapping between MCAL drivers and RTE ports (Vector template, project-configured)."
---


import { Badge } from '@astrojs/starlight/components';

# I/O Hardware Abstraction

Repo directory: `IoHwAb/` · Layer: `bsw`

<Badge text="Vector-provided · customised" variant="caution" />

## Purpose and responsibility

I/O Hardware Abstraction: project signal mapping between MCAL drivers and RTE ports (Vector template, project-configured).

## Origin

**Vector-provided · customised.** Vector IoHwAb template customised for this ECU (project mapping lives in `_Ford_T3T6_Eps_Impl_A/src/IoHwAb_30.c`).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `include/` (1 entries): `IoHwAb.h`
- `autosar/` (2 entries): `IoHwAb_bswmd.arxml`, `IoHwAb_preo.arxml`
- `make/` (4 entries): `IOHWAB_cfg.mak`, `IOHWAB_check.mak`, `IOHWAB_defs.mak`, `IOHWAB_rules.mak`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`, `IoHwAb.gpj`
- `doc/` (2 entries): `IoHwAb Peer Review Checklists.xlsm`, `TechnicalReference_IoHwAb.pdf`

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

- [TechnicalReference_IoHwAb.pdf](./technicalreference-iohwab/)

## Repository location

Repo path: `IoHwAb/` — subfolders present: `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
