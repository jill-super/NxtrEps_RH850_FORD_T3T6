---
title: "Serial Peripheral Interface Driver"
description: "Spi: Renesas P1x-C SPI handler/driver: synchronous serial transfers (e.g. gate-driver, sensor links)."
---


import { Badge } from '@astrojs/starlight/components';

# Serial Peripheral Interface Driver

Repo directory: `Spi/` · Layer: `mcal`

<Badge text="Renesas-provided · MCAL" variant="note" />

## Purpose and responsibility

Renesas P1x-C SPI handler/driver: synchronous serial transfers (e.g. gate-driver, sensor links).

## Origin

**Renesas-provided · MCAL.** Renesas copyright header in `Spi/src/Spi.c` (P1x-C/X1x MCAL delivery).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (6 entries): `Spi.c`, `Spi_Driver.c`, `Spi_Irq.c`, `Spi_Ram.c`, `Spi_Scheduler.c`, `Spi_Version.c`
- `include/` (10 entries): `Spi.h`, `Spi_Driver.h`, `Spi_Irq.h`, `Spi_LTTypes.h`, `Spi_PBTypes.h`, `Spi_Ram.h`, `Spi_RegWrite.h`, `Spi_Scheduler.h`, `Spi_Types.h`, `Spi_Version.h`
- `autosar/` (2 entries): `R403_SPI_P1X-C.arxml`, `Spi_bswmd_rec.arxml`
- `make/` (3 entries): `renesas_spi_check.mak`, `renesas_spi_defs.mak`, `renesas_spi_rules.mak`
- `generate/` (5 entries): `CommonHelper`, `R403_SPI_P1x-C_BSWMDT.arxml`, `Template`, `Validate`, `config.xml`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`, `Spi.gpj`
- `doc/` (4 entries): `R20UT3659EJ0100-AUTOSAR.pdf`, `R20UT3660EJ0100-AUTOSAR.pdf`, `Spi Integration Manual.doc`, `Spi Peer Review Checklist.xlsm`

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

- [R20UT3659EJ0100-AUTOSAR.pdf](./r20ut3659ej0100-autosar/)
- [R20UT3660EJ0100-AUTOSAR.pdf](./r20ut3660ej0100-autosar/)
- [Spi Integration Manual.doc](./spi-integration-manual/)

## Repository location

Repo path: `Spi/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`, `generate/`.
