---
title: "Handwheel Torque 1 Measurement (CM660A)"
description: "CM660A_HwTq1Meas_Impl: Complex driver `HwTq1Meas` (CM660A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# Handwheel Torque 1 Measurement (CM660A)

Repo directory: `CM660A_HwTq1Meas_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `HwTq1Meas` (CM660A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM660A_HwTq1Meas_Impl/src/CDD_HwTq1Meas.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `CDD_HwTq1Meas.c`
- `include/` (1 entries): `CDD_HwTq1Meas.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `HwTq1Meas.dcf`, `HwTq1Meas_attr_def.xml`, `HwTq1Meas_bswmd.arxml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (7 entries): `CM660A_HwTq1Meas_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`, `template`
- `doc/` (4 entries): `HwTq1Meas_IntegrationManual.doc`, `HwTq1Meas_MDD.docx`, `HwTq1Meas_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [HwTq1Meas_IntegrationManual.doc](./hwtq1meas-integrationmanual/)
- [HwTq1Meas_MDD.docx](./hwtq1meas-mdd/)

## Repository location

Repo path: `CM660A_HwTq1Meas_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
