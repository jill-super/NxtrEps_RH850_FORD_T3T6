---
title: "Motor Angle 6 Measurement (ES243A)"
description: "ES243A_MotAg6Meas_Impl: EPS system service `MotAg6Meas` (ES243A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Motor Angle 6 Measurement (ES243A)

Repo directory: `ES243A_MotAg6Meas_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `MotAg6Meas` (ES243A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES243A_MotAg6Meas_Impl/src/CDD_MotAg6Meas.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_MotAg6Meas.c`, `CDD_MotAg6Meas_MotCtrl.c`
- `include/` (2 entries): `CDD_MotAg6Meas.h`, `CDD_MotAg6Meas_MotCtrl_MemMap.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `MotAg6Meas.dcf`, `MotAg6Meas_attr_def.xml`, `MotAg6Meas_bswmd.arxml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (7 entries): `Component.dpa`, `ES243A_MotAg6Meas_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`, `template`
- `doc/` (4 entries): `MotAg6Meas_IntegrationManual.doc`, `MotAg6Meas_MDD.docx`, `MotAg6Meas_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [MotAg6Meas_IntegrationManual.doc](./motag6meas-integrationmanual/)
- [MotAg6Meas_MDD.docx](./motag6meas-mdd/)

## Repository location

Repo path: `ES243A_MotAg6Meas_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
