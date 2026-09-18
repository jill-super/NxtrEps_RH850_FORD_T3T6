---
title: "Development Error Tracer"
description: "Det: Development Error Tracer: hook for API misuse reporting during development (compiled out in production)."
---


import { Badge } from '@astrojs/starlight/components';

# Development Error Tracer

Repo directory: `Det/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

Development Error Tracer: hook for API misuse reporting during development (compiled out in production).

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `Det/src/Det.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `Det.c`
- `include/` (1 entries): `Det.h`
- `autosar/` (3 entries): `Det_bswmd.arxml`, `Ford`, `GM`
- `make/` (4 entries): `Det_cfg.mak`, `Det_check.mak`, `Det_defs.mak`, `Det_rules.mak`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Det.gpj`, `Integrate.bat`, `IntegrationCopy`
- `doc/` (2 entries): `Det Peer Review Checklists.xlsm`, `TechnicalReference_Det.pdf`

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

- [TechnicalReference_Det.pdf](./technicalreference-det/)

## Repository location

Repo path: `Det/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
