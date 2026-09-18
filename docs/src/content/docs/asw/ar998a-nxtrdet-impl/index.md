---
title: "Nexteer Development Error Tracer (AR998A)"
description: "AR998A_NxtrDet_Impl: Project development-error hook (NxtrDet) used in place of plain Det in custom code."
---


import { Badge } from '@astrojs/starlight/components';

# Nexteer Development Error Tracer (AR998A)

Repo directory: `AR998A_NxtrDet_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Project development-error hook (NxtrDet) used in place of plain Det in custom code.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `AR998A_NxtrDet_Impl/src/NxtrDet.h` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `include/` (1 entries): `NxtrDet.h`
- `tools/` (5 entries): `AR998A_NxtrDet_Impl.gpj`, `CreateGHSProject.bat`, `Polyspace`, `QAC`, `contract`
- `doc/` (7 entries): `AR998A_NxtrDet_DDReport.txt`, `AR998A_NxtrDet_DataDict.m`, `NxtrDet Integration Manual.doc`, `NxtrDet Module Design Document.docx`, `NxtrDet Peer Review Checklists.xlsm`, `Polyspace_Results`, `QAC_Results`

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

- [AR998A_NxtrDet_DDReport.txt](./ar998a-nxtrdet-ddreport/)
- [NxtrDet Integration Manual.doc](./nxtrdet-integration-manual/)
- [NxtrDet Module Design Document.docx](./nxtrdet-module-design-document/)

## Repository location

Repo path: `AR998A_NxtrDet_Impl/` — subfolders present: `include/`, `doc/`, `tools/`.
