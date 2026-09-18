---
title: "Digital Input/Output Driver"
description: "Dio: Renesas P1x-C DIO driver: discrete digital I/O channels/ports."
---


import { Badge } from '@astrojs/starlight/components';

# Digital Input/Output Driver

Repo directory: `Dio/` · Layer: `mcal`

<Badge text="Renesas-provided · MCAL" variant="note" />

## Purpose and responsibility

Renesas P1x-C DIO driver: discrete digital I/O channels/ports.

## Origin

**Renesas-provided · MCAL.** Renesas copyright header in `Dio/src/Dio.c` (P1x-C/X1x MCAL delivery).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (3 entries): `Dio.c`, `Dio_Ram.c`, `Dio_Version.c`
- `include/` (6 entries): `Dio.h`, `Dio_Debug.h`, `Dio_PBTypes.h`, `Dio_Ram.h`, `Dio_RegWrite.h`, `Dio_Version.h`
- `autosar/` (3 entries): `Dio_bswmd_rec.arxml`, `R403_DIO_P1X-C_73.arxml`, `R403_DIO_P1X-C_74.arxml`
- `make/` (3 entries): `renesas_dio_check.mak`, `renesas_dio_defs.mak`, `renesas_dio_rules.mak`
- `generate/` (5 entries): `CommonHelper`, `R403_DIO_P1x-C_BSWMDT.arxml`, `Template`, `Validate`, `config.xml`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Dio.gpj`, `Integrate.bat`, `IntegrationCopy`
- `doc/` (4 entries): `Dio Integration Manual.doc`, `Dio Peer Review Checklist.xlsm`, `R20UT3639EJ0102-AUTOSAR.pdf`, `R20UT3640EJ0102-AUTOSAR.pdf`

## Generated code and configuration

- DaVinci `generate/` output shipped with the module.
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

- [Dio Integration Manual.doc](./dio-integration-manual/)
- [R20UT3639EJ0102-AUTOSAR.pdf](./r20ut3639ej0102-autosar/)
- [R20UT3640EJ0102-AUTOSAR.pdf](./r20ut3640ej0102-autosar/)

## Repository location

Repo path: `Dio/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`, `generate/`.
