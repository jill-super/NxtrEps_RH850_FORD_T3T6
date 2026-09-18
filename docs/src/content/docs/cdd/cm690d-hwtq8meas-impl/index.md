---
title: "Handwheel Torque 8 Measurement (CM690D)"
description: "CM690D_HwTq8Meas_Impl: Complex driver `HwTq8Meas` (CM690D): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# Handwheel Torque 8 Measurement (CM690D)

Repo directory: `CM690D_HwTq8Meas_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `HwTq8Meas` (CM690D): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM690D_HwTq8Meas_Impl/src/CDD_HwTq8Meas.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `CDD_HwTq8Meas.c`
- `include/` (1 entries): `CDD_HwTq8Meas.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `HwTq8Meas.dcf`, `HwTq8Meas_attr_def.xml`, `HwTq8Meas_bswmd.arxml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (7 entries): `CM690D_HwTq8Meas_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`, `template`
- `doc/` (4 entries): `HwTq8Meas_IntegrationManual.doc`, `HwTq8Meas_MDD.doc`, `HwTq8Meas_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [HwTq8Meas_IntegrationManual.doc](./hwtq8meas-integrationmanual/)
- [HwTq8Meas_MDD.doc](./hwtq8meas-mdd/)

## Repository location

Repo path: `CM690D_HwTq8Meas_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
