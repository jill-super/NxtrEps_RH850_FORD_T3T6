---
title: "Flash Driver"
description: "Fls: Renesas P1x-C Flash driver: internal code/data flash erase/write/read jobs."
---


import { Badge } from '@astrojs/starlight/components';

# Flash Driver

Repo directory: `Fls/` · Layer: `mcal`

<Badge text="Renesas-provided · MCAL" variant="note" />

## Purpose and responsibility

Renesas P1x-C Flash driver: internal code/data flash erase/write/read jobs.

## Origin

**Renesas-provided · MCAL.** Renesas copyright header in `Fls/src/Fls.c` (P1x-C/X1x MCAL delivery).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (5 entries): `Fls.c`, `Fls_Internal.c`, `Fls_Private_Fcu.c`, `Fls_Ram.c`, `Fls_Version.c`
- `include/` (9 entries): `Fls.h`, `Fls_Debug.h`, `Fls_Internal.h`, `Fls_PBTypes.h`, `Fls_Private_Fcu.h`, `Fls_Ram.h`, `Fls_RegWrite.h`, `Fls_Types.h`, `Fls_Version.h`
- `autosar/` (2 entries): `Fls_bswmd_rec.arxml`, `R403_FLS_P1X-C.arxml`
- `make/` (3 entries): `renesas_fls_check.mak`, `renesas_fls_defs.mak`, `renesas_fls_rules.mak`
- `generate/` (5 entries): `CommonHelper`, `R403_FLS_P1x-C_BSWMDT.arxml`, `Template`, `Validate`, `config.xml`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Fls.gpj`, `Integrate.bat`, `IntegrationCopy`
- `doc/` (4 entries): `Fls Integration Manual.doc`, `Fls Peer Review Checklist.xlsm`, `R20UT3641EJ0100-AUTOSAR.pdf`, `R20UT3642EJ0100-AUTOSAR.pdf`

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

- [Fls Integration Manual.doc](./fls-integration-manual/)
- [R20UT3641EJ0100-AUTOSAR.pdf](./r20ut3641ej0100-autosar/)
- [R20UT3642EJ0100-AUTOSAR.pdf](./r20ut3642ej0100-autosar/)

## Repository location

Repo path: `Fls/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`, `generate/`.
