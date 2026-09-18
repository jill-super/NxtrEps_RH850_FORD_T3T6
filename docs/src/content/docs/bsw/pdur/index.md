---
title: "PDU Router"
description: "PduR: PDU Router: static routing of I-PDUs between Com/Dcm/CanTp/CanIf/XCP."
---


import { Badge } from '@astrojs/starlight/components';

# PDU Router

Repo directory: `PduR/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

PDU Router: static routing of I-PDUs between Com/Dcm/CanTp/CanIf/XCP.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `PduR/src/PduR.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `PduR.c`
- `include/` (1 entries): `PduR.h`
- `autosar/` (2 entries): `PduR_bswmd.arxml`, `PduR_preo.arxml`
- `make/` (4 entries): `PduR_cfg.mak`, `PduR_check.mak`, `PduR_defs.mak`, `PduR_rules.mak`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`, `PduR.gpj`
- `doc/` (2 entries): `Pdur Peer Review Checklists.xlsm`, `TechnicalReference_PduR.pdf`

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

- [TechnicalReference_PduR.pdf](./technicalreference-pdur/)

## Repository location

Repo path: `PduR/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
