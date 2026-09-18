---
title: "Motor Angle 2 Measurement (ES241A)"
description: "ES241A_MotAg2Meas_Impl: EPS system service `MotAg2Meas` (ES241A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Motor Angle 2 Measurement (ES241A)

Repo directory: `ES241A_MotAg2Meas_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `MotAg2Meas` (ES241A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES241A_MotAg2Meas_Impl/src/MotAg2Meas.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `MotAg2Meas.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `MotAg2Meas.dcf`, `MotAg2Meas_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (12 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `ES241A_MotAg2Meas_Impl.gpj`, `MotAg2Meas.dpa`, `Polyspace`, `QAC`, `RteGen.bat`, `contract`
- `doc/` (6 entries): `MotAg2Meas_IntegrationManual.doc`, `MotAg2Meas_MDD.docx`, `MotAg2Meas_Review.xlsm`, `Polyspace_Results`, `QAC_Results`, `requirements.csv`

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

- [MotAg2Meas_IntegrationManual.doc](./motag2meas-integrationmanual/)
- [MotAg2Meas_MDD.docx](./motag2meas-mdd/)

## Repository location

Repo path: `ES241A_MotAg2Meas_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
