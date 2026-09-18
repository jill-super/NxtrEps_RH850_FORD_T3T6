---
title: "System State Mode (ES100A)"
description: "ES100A_SysStMod_Impl: EPS system service `SysStMod` (ES100A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# System State Mode (ES100A)

Repo directory: `ES100A_SysStMod_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `SysStMod` (ES100A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES100A_SysStMod_Impl/src/SysStMod.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `SysStMod.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `SysStMod.dcf`, `SysStMod_attr_def.xml`
- `tools/` (12 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `ES100A_SysStMod_Impl.gpj`, `Polyspace`, `QAC`, `RteGen.bat`, `SysStMod.dpa`, `contract`
- `doc/` (6 entries): `Polyspace_Results`, `QAC_Results`, `SysStMod_IntegrationManual.doc`, `SysStMod_MDD.doc`, `SysStMod_PeerReviewChecklist.xlsm`, `requirements.csv`

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

- [SysStMod_IntegrationManual.doc](./sysstmod-integrationmanual/)
- [SysStMod_MDD.doc](./sysstmod-mdd/)

## Repository location

Repo path: `ES100A_SysStMod_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
