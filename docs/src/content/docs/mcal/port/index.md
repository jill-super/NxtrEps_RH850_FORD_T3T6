---
title: "Port Driver"
description: "Port: Renesas P1x-C Port driver: pin multiplexing, direction and pad configuration."
---


import { Badge } from '@astrojs/starlight/components';

# Port Driver

Repo directory: `Port/` · Layer: `mcal`

<Badge text="Renesas-provided · MCAL" variant="note" />

## Purpose and responsibility

Renesas P1x-C Port driver: pin multiplexing, direction and pad configuration.

## Origin

**Renesas-provided · MCAL.** Renesas copyright header in `Port/src/Port.c` (P1x-C/X1x MCAL delivery).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (3 entries): `Port.c`, `Port_Ram.c`, `Port_Version.c`
- `include/` (7 entries): `Port.h`, `Port_Debug.h`, `Port_PBTypes.h`, `Port_Ram.h`, `Port_RegWrite.h`, `Port_Types.h`, `Port_Version.h`
- `autosar/` (3 entries): `Port_bswmd_rec.arxml`, `R403_PORT_P1X-C_73.arxml`, `R403_PORT_P1X-C_74.arxml`
- `make/` (3 entries): `renesas_port_check.mak`, `renesas_port_defs.mak`, `renesas_port_rules.mak`
- `generate/` (5 entries): `CommonHelper`, `R403_PORT_P1x-C_BSWMDT.arxml`, `Template`, `Validate`, `config.xml`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`, `Port.gpj`
- `doc/` (4 entries): `Port Integration Manual.doc`, `Port Peer Review Checklist.xlsm`, `R20UT3653EJ0102-AUTOSAR.pdf`, `R20UT3654EJ0102-AUTOSAR.pdf`

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

- [Port Integration Manual.doc](./port-integration-manual/)
- [R20UT3653EJ0102-AUTOSAR.pdf](./r20ut3653ej0102-autosar/)
- [R20UT3654EJ0102-AUTOSAR.pdf](./r20ut3654ej0102-autosar/)

## Repository location

Repo path: `Port/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`, `generate/`.
