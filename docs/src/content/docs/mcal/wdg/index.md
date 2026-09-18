---
title: "Watchdog Driver"
description: "Wdg: Renesas X1x watchdog driver A: hardware watchdog triggering and mode control."
---


import { Badge } from '@astrojs/starlight/components';

# Watchdog Driver

Repo directory: `Wdg/` · Layer: `mcal`

<Badge text="Renesas-provided · MCAL" variant="note" />

## Purpose and responsibility

Renesas X1x watchdog driver A: hardware watchdog triggering and mode control.

## Origin

**Renesas-provided · MCAL.** Renesas copyright header in `Wdg/src/Wdg_59_DriverA.c` (P1x-C/X1x MCAL delivery).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (5 entries): `Wdg_59_DriverA.c`, `Wdg_59_DriverA_Irq.c`, `Wdg_59_DriverA_Private.c`, `Wdg_59_DriverA_Ram.c`, `Wdg_59_DriverA_Version.c`
- `include/` (9 entries): `Wdg_59_DriverA.h`, `Wdg_59_DriverA_Debug.h`, `Wdg_59_DriverA_Irq.h`, `Wdg_59_DriverA_PBTypes.h`, `Wdg_59_DriverA_Private.h`, `Wdg_59_DriverA_Ram.h`, `Wdg_59_DriverA_RegWrite.h`, `Wdg_59_DriverA_Types.h`, `Wdg_59_DriverA_Version.h`
- `autosar/` (2 entries): `R403_WDG_DriverA_P1X-C.arxml`, `WdgDriverA_bswmd_rec.arxml`
- `make/` (3 entries): `renesas_wdg_check.mak`, `renesas_wdg_defs.mak`, `renesas_wdg_rules.mak`
- `generate/` (5 entries): `CommonHelper`, `R403_WDG_P1x-C_BSWMDT.arxml`, `Template`, `Validate`, `config.xml`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`, `Wdg.gpj`
- `doc/` (4 entries): `R20UT3661EJ0100-AUTOSAR.pdf`, `R20UT3662EJ0100-AUTOSAR.pdf`, `Wdg Integration Manual.doc`, `Wdg Peer Review Checklist.xlsm`

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

- [R20UT3661EJ0100-AUTOSAR.pdf](./r20ut3661ej0100-autosar/)
- [R20UT3662EJ0100-AUTOSAR.pdf](./r20ut3662ej0100-autosar/)
- [Wdg Integration Manual.doc](./wdg-integration-manual/)

## Repository location

Repo path: `Wdg/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`, `generate/`.
