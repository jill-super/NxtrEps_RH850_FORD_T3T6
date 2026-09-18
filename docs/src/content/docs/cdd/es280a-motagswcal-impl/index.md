---
title: "Motor Angle Software Calibration (ES280A)"
description: "ES280A_MotAgSwCal_Impl: EPS system service `MotAgSwCal` (ES280A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Motor Angle Software Calibration (ES280A)

Repo directory: `ES280A_MotAgSwCal_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `MotAgSwCal` (ES280A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES280A_MotAgSwCal_Impl/src/CDD_MotAgSwCal.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (3 entries): `CDD_MotAgSwCal.c`, `CDD_MotAgSwCal_MotCtrl.c`, `CDD_MotAgSwCal_private.c`
- `include/` (3 entries): `CDD_MotAgSwCal.h`, `CDD_MotAgSwCal_MotCtrl_MemMap.h`, `CDD_MotAgSwCal_private.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `MotAgSwCal.dcf`, `MotAgSwCal_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `Component.dpa`, `ES280A_MotAgSwCal_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `MotAgSwCal_IntegrationManual.doc`, `MotAgSwCal_MDD.docx`, `MotAgSwCal_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [MotAgSwCal_IntegrationManual.doc](./motagswcal-integrationmanual/)
- [MotAgSwCal_MDD.docx](./motagswcal-mdd/)

## Repository location

Repo path: `ES280A_MotAgSwCal_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
