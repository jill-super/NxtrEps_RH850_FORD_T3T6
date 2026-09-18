---
title: "Renesas MCAL Support"
description: "RenesasMcalSuprt: Renesas MCAL support bundle: compiler abstraction, device headers and integration helpers."
---


import { Badge } from '@astrojs/starlight/components';

# Renesas MCAL Support

Repo directory: `RenesasMcalSuprt/` · Layer: `mcal`

<Badge text="Renesas-provided · MCAL" variant="note" />

## Purpose and responsibility

Renesas MCAL support bundle: compiler abstraction, device headers and integration helpers.

## Origin

**Renesas-provided · MCAL.** Renesas MCAL support bundle (compiler abstraction, device headers, integration helpers under `include/`).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `include/` (2 entries): `P1M`, `P1MC`
- `tools/` (7 entries): `P1M`, `P1MC`, `RenesasMcalSuprt_P1MC_4.02.01.D.gpj`, `RenesasMcalSuprt_P1M_4.00.04.gpj`, `RenesasMcalSuprt_P1M_4.01.01.D.gpj`, `RenesasMcalSuprt_P1M_4.02.01.D.gpj`, `RenesasMcalSuprt_P1M_E4.03.gpj`
- `doc/` (4 entries): `P1M`, `P1MC`, `RenesasMcalSuprt Integration Manual.doc`, `RenesasMcalSuprt Peer Review Checklists.xlsm`

## Generated code and configuration

- No generator/contract folders observed.

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

- [GettingStarted_MCAL_Drivers_X1x.pdf](./gettingstarted-mcal-drivers-x1x/)
- [KnownIssues_P1x_R403_2015_CW23.pdf](./knownissues-p1x-r403-2015-cw23/)
- [Releasenotes_P1x_FULL_R403_Ver4.00.04.pdf](./releasenotes-p1x-full-r403-ver4-00-04/)
- [readme.txt](./readme/)
- [R20UT3752EJ0100-AUTOSAR.pdf](./r20ut3752ej0100-autosar/)
- [R20UT3753EJ0100-AUTOSAR.pdf](./r20ut3753ej0100-autosar/)
- [Releasenotes_P1x_SPAL_R403_Ver4.01.01.D.pdf](./releasenotes-p1x-spal-r403-ver4-01-01-d/)
- [readme.txt](./readme-2/)
- [LICENSE.txt](./license/)
- [R20UT3752EJ0101-AUTOSAR.pdf](./r20ut3752ej0101-autosar/)
- [R20UT3753EJ0101-AUTOSAR.pdf](./r20ut3753ej0101-autosar/)
- [Releasenotes_P1x_SPAL_R403_Ver4.02.01.D.pdf](./releasenotes-p1x-spal-r403-ver4-02-01-d/)
- [readme.txt](./readme-3/)
- [R20UT3827EJ0100-AUTOSAR.pdf](./r20ut3827ej0100-autosar/)
- [R20UT3828EJ0100-AUTOSAR.pdf](./r20ut3828ej0100-autosar/)
- [Releasenotes_P1M-C_SPAL_R403_Ver4.02.00.D.pdf](./releasenotes-p1m-c-spal-r403-ver4-02-00-d/)
- [readme.txt](./readme-4/)
- [R20UT3827EJ0101-AUTOSAR.pdf](./r20ut3827ej0101-autosar/)
- [R20UT3828EJ0101-AUTOSAR.pdf](./r20ut3828ej0101-autosar/)
- [Releasenotes_P1M-C_SPAL_R403_Ver4.02.01.D.pdf](./releasenotes-p1m-c-spal-r403-ver4-02-01-d/)
- [readme.txt](./readme-5/)
- [RenesasMcalSuprt Integration Manual.doc](./renesasmcalsuprt-integration-manual/)

## Repository location

Repo path: `RenesasMcalSuprt/` — subfolders present: `include/`, `doc/`, `tools/`.
