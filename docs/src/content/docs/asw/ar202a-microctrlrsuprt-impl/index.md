---
title: "Microcontroller support library (AR202A)"
description: "AR202A_MicroCtrlrSuprt_Impl: Microcontroller support library and header-generation scripts (P1x-C register defines)."
---


import { Badge } from '@astrojs/starlight/components';

# Microcontroller support library (AR202A)

Repo directory: `AR202A_MicroCtrlrSuprt_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Microcontroller support library and header-generation scripts (P1x-C register defines).

## Origin

**Custom · Nexteer in-house.** No compilable source in this folder (headers/config/tools only); treated as project-owned glue.

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `include/` (2 entries): `P1M`, `P1XC`
- `tools/` (7 entries): `AR202A_MicroCtrlrSuprt_Impl_P1M_R7F701311.gpj`, `AR202A_MicroCtrlrSuprt_Impl_P1XC_R7F701373.gpj`, `ConversionFiles`, `P1M`, `P1XC`, `Polyspace`, `contract`
- `doc/` (4 entries): `MicroCtrlrSuprt Integration Manual.doc`, `MicroCtrlrSuprt Module Design Document.docx`, `MicroCtrlrSuprt Peer Review Checklists.xlsm`, `Polyspace_Results.zip`

## Generated code and configuration

- RTE contracts: `tools/contract/` (input interfaces for this SW-C).

## Public API

Application/CDD code exposes its interface through RTE ports and `include/` types; entry points are the SW-C runnables/CDD services implemented under `src/` (see the file list above and the module MDD for signatures).

## Usage example

```c
/* Typical SW-C runnable shape (names vary per component): */
void Swc_Runnable(void) {
    /* Rte_IRead inputs -> control law -> Rte_IWrite outputs */
}
```

## Dependencies

- Consumes platform libraries (`AR*`), global parameters (`*GlbPrm`) and RTE ports.
- Fault handling via `FltInj`/diagnostic manager where present; calibration via DataDict databooks.

## Converted documentation

- [MicroCtrlrSuprt Integration Manual.doc](./microctrlrsuprt-integration-manual/)
- [MicroCtrlrSuprt Module Design Document.docx](./microctrlrsuprt-module-design-document/)
- [HeaderGen.docx](./headergen/)

## Repository location

Repo path: `AR202A_MicroCtrlrSuprt_Impl/` — subfolders present: `include/`, `doc/`, `tools/`.
