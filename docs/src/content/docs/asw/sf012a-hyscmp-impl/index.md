---
title: "Hysteresis Compensation (SF012A)"
description: "SF012A_HysCmp_Impl: Application SW-C `HysCmp` (SF012A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and v"
---


import { Badge } from '@astrojs/starlight/components';

# Hysteresis Compensation (SF012A)

Repo directory: `SF012A_HysCmp_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `HysCmp` (SF012A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF012A_HysCmp_Impl/src/HysCmp.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `HysCmp.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `HysCmp.dcf`, `HysCmp_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (12 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `HysCmp.dpa`, `Polyspace`, `QAC`, `RteGen.bat`, `SF012A_HysCmp_Impl.gpj`, `contract`
- `doc/` (5 entries): `HysCmp_DesignReview.xlsm`, `HysCmp_IntegrationManual.doc`, `HysCmp_MDD.docx`, `Polyspace_Results.zip`, `QAC_Results`

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

- [HysCmp_IntegrationManual.doc](./hyscmp-integrationmanual/)
- [HysCmp_MDD.docx](./hyscmp-mdd/)

## Repository location

Repo path: `SF012A_HysCmp_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
