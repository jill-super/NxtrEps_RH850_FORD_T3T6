---
title: "Vector BSW Support"
description: "VectorBswSuprt: Vector BSW support bundle: VStdLib and MICROSAR integration helpers referenced by generated code."
---


import { Badge } from '@astrojs/starlight/components';

# Vector BSW Support

Repo directory: `VectorBswSuprt/` · Layer: `integration`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

Vector BSW support bundle: VStdLib and MICROSAR integration helpers referenced by generated code.

## Origin

**Vector-provided · MICROSAR.** Vector support bundle (VStdLib / MICROSAR helpers); see `include/` version folders.

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (4 entries): `01.03.00_03.08.00`, `01.04.00_03.08.00`, `02.00.00`, `02.00.02`
- `include/` (4 entries): `01.03.00_03.08.00`, `01.04.00_03.08.00`, `02.00.00`, `02.00.02`
- `make/` (2 entries): `02.00.00`, `02.00.02`
- `tools/` (5 entries): `VStdLib_01.03.00_03.08.00.gpj`, `VStdLib_01.04.00_03.08.00.gpj`, `VStdLib_02.00.00.gpj`, `VStdLib_02.00.02.gpj`, `template`
- `doc/` (5 entries): `01.04.00_03.08.00`, `02.00.00`, `02.00.02`, `VectorBswSuprt Integration Manual.doc`, `VectorBswSuprt Peer Review Checklists.xlsm`

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

- [AN-ISC-2-1081_Interrupt_Control_VStdLib.pdf](./an-isc-2-1081-interrupt-control-vstdlib/)
- [TechnicalReference_VStdLib.pdf](./technicalreference-vstdlib/)
- [TechnicalReference_VStdLib_GenericAsr.pdf](./technicalreference-vstdlib-genericasr/)
- [TechnicalReference_VStdLib_GenericAsr.pdf](./technicalreference-vstdlib-genericasr-2/)
- [VectorBswSuprt Integration Manual.doc](./vectorbswsuprt-integration-manual/)

## Repository location

Repo path: `VectorBswSuprt/` — subfolders present: `src/`, `include/`, `doc/`, `tools/`, `make/`.
