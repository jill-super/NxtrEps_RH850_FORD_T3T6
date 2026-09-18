---
title: "Vehicle Speed Limiter (SF016A)"
description: "SF016A_VehSpdLimr_Impl: Application SW-C `VehSpdLimr` (SF016A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook a"
---


import { Badge } from '@astrojs/starlight/components';

# Vehicle Speed Limiter (SF016A)

Repo directory: `SF016A_VehSpdLimr_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `VehSpdLimr` (SF016A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF016A_VehSpdLimr_Impl/src/VehSpdLimr.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `VehSpdLimr.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `VehSpdLimr.dcf`, `VehSpdLimr_attr_def.xml`
- `tools/` (12 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `Polyspace`, `QAC`, `RteGen.bat`, `SF016A_VehSpdLimr_Impl.gpj`, `VehSpdLimr.dpa`, `contract`
- `doc/` (5 entries): `Polyspace_Results`, `QAC_Results`, `VehSpdLimr_DesignReview.xlsm`, `VehSpdLimr_IntegrationManual.doc`, `VehSpdLimr_MDD.docx`

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

- [VehSpdLimr_IntegrationManual.doc](./vehspdlimr-integrationmanual/)
- [VehSpdLimr_MDD.docx](./vehspdlimr-mdd/)

## Repository location

Repo path: `SF016A_VehSpdLimr_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
