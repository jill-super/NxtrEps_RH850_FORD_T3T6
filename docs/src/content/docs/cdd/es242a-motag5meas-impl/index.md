---
title: "Motor Angle 5 Measurement (ES242A)"
description: "ES242A_MotAg5Meas_Impl: EPS system service `MotAg5Meas` (ES242A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Motor Angle 5 Measurement (ES242A)

Repo directory: `ES242A_MotAg5Meas_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `MotAg5Meas` (ES242A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES242A_MotAg5Meas_Impl/src/CDD_MotAg5Meas.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_MotAg5Meas.c`, `CDD_MotAg5Meas_MotCtrl.c`
- `include/` (2 entries): `CDD_MotAg5Meas.h`, `CDD_MotAg5Meas_MotCtrl_MemMap.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `MotAg5Meas.dcf`, `MotAg5Meas_attr_def.xml`, `MotAg5Meas_bswmd.arxml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (7 entries): `Component.dpa`, `ES242A_MotAg5Meas_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`, `template`
- `doc/` (4 entries): `MotAg5Meas_IntegrationManual.doc`, `MotAg5Meas_MDD.docx`, `MotAg5Meas_PeerReviewChecklist.xlsm`, `Polyspace`

## Generated code and configuration

- Local generation output: `tools/local/generate/`.
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

- [MotAg5Meas_IntegrationManual.doc](./motag5meas-integrationmanual/)
- [MotAg5Meas_MDD.docx](./motag5meas-mdd/)

## Repository location

Repo path: `ES242A_MotAg5Meas_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
