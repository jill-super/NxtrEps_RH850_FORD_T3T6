---
title: "Fault Injection (DF001A)"
description: "DF001A_FltInj_Impl: Development/test support component `FltInj` (DF001A): fault-injection or software-programming hooks used for validation."
---


import { Badge } from '@astrojs/starlight/components';

# Fault Injection (DF001A)

Repo directory: `DF001A_FltInj_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Development/test support component `FltInj` (DF001A): fault-injection or software-programming hooks used for validation.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `DF001A_FltInj_Impl/src/FltInj.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `FltInj.c`
- `include/` (1 entries): `FltInj.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `FltInj.dcf`, `FltInj_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (12 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `DF001A_FltInj_Impl.gpj`, `FltInj.dpa`, `Polyspace`, `QAC`, `RteGen.bat`, `contract`
- `doc/` (5 entries): `FltInj_IntegrationManual.doc`, `FltInj_MDD.docx`, `FltInj_PeerReview.xlsm`, `Polyspace_Results`, `QAC_Results`

## Generated code and configuration

- RTE contracts: `tools/contract/` (input interfaces for this SW-C).
- AUTOSAR model fragments: `autosar/` (`.arxml`/`.dpa`/`.dcf`).

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

- [FltInj_IntegrationManual.doc](./fltinj-integrationmanual/)
- [FltInj_MDD.docx](./fltinj-mdd/)

## Repository location

Repo path: `DF001A_FltInj_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
