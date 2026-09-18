---
title: "Microcontroller Unit Driver"
description: "Mcu: Renesas P1x-C MCU driver: clock, PLL, reset, power and mode initialisation."
---


import { Badge } from '@astrojs/starlight/components';

# Microcontroller Unit Driver

Repo directory: `Mcu/` · Layer: `mcal`

<Badge text="Renesas-provided · MCAL" variant="note" />

## Purpose and responsibility

Renesas P1x-C MCU driver: clock, PLL, reset, power and mode initialisation.

## Origin

**Renesas-provided · MCAL.** Renesas copyright header in `Mcu/src/Mcu.c` (P1x-C/X1x MCAL delivery).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (4 entries): `Mcu.c`, `Mcu_Irq.c`, `Mcu_Ram.c`, `Mcu_Version.c`
- `include/` (8 entries): `Mcu.h`, `Mcu_Debug.h`, `Mcu_Irq.h`, `Mcu_PBTypes.h`, `Mcu_Ram.h`, `Mcu_RegWrite.h`, `Mcu_Types.h`, `Mcu_Version.h`
- `autosar/` (2 entries): `Mcu_bswmd_rec.arxml`, `R403_MCU_P1X-C.arxml`
- `make/` (3 entries): `renesas_mcu_check.mak`, `renesas_mcu_defs.mak`, `renesas_mcu_rules.mak`
- `generate/` (5 entries): `CommonHelper`, `R403_MCU_P1x-C_BSWMDT.arxml`, `Template`, `Validate`, `config.xml`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`, `Mcu.gpj`
- `doc/` (4 entries): `Mcu Integration Manual.doc`, `Mcu Peer Review Checklist.xlsm`, `R20UT3651EJ0100-AUTOSAR.pdf`, `R20UT3652EJ0100-AUTOSAR.pdf`

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

- [Mcu Integration Manual.doc](./mcu-integration-manual/)
- [R20UT3651EJ0100-AUTOSAR.pdf](./r20ut3651ej0100-autosar/)
- [R20UT3652EJ0100-AUTOSAR.pdf](./r20ut3652ej0100-autosar/)

## Repository location

Repo path: `Mcu/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`, `generate/`.
