---
title: "Motor Angle Compensation (ES247A)"
description: "ES247A_MotAgCmp_Impl: EPS system service `MotAgCmp` (ES247A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Motor Angle Compensation (ES247A)

Repo directory: `ES247A_MotAgCmp_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `MotAgCmp` (ES247A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES247A_MotAgCmp_Impl/src/CDD_MotAgCmp.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_MotAgCmp.c`, `CDD_MotAgCmp_MotCtrl.c`
- `include/` (2 entries): `CDD_MotAgCmp.h`, `CDD_MotAgCmp_MotCtrl_MemMap.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `MotAgCmp.dcf`, `MotAgCmp_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (12 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `ES247A_MotAgCmp_Impl.gpj`, `MotAgCmp.dpa`, `Polyspace`, `QAC`, `RteGen.bat`, `contract`
- `doc/` (5 entries): `MotAgCmp_DesignReview.xlsm`, `MotAgCmp_IntegrationManual.doc`, `MotAgCmp_MDD.doc`, `Polyspace_Results`, `QAC_Results`

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

- [MotAgCmp_IntegrationManual.doc](./motagcmp-integrationmanual/)
- [MotAgCmp_MDD.doc](./motagcmp-mdd/)

## Repository location

Repo path: `ES247A_MotAgCmp_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
