---
title: "Handwheel Angle 1 Measurement (CM670A)"
description: "CM670A_HwAg1Meas_Impl: Complex driver `HwAg1Meas` (CM670A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# Handwheel Angle 1 Measurement (CM670A)

Repo directory: `CM670A_HwAg1Meas_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `HwAg1Meas` (CM670A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM670A_HwAg1Meas_Impl/src/HwAg1Meas.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `HwAg1Meas.c`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `HwAg1Meas.dcf`, `HwAg1Meas_attr_def.xml`, `HwAg1Meas_bswmd.arxml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (7 entries): `CM670A_HwAg1Meas_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`, `template`
- `doc/` (4 entries): `HwAg1Meas_IntegrationManual.doc`, `HwAg1Meas_MDD.docx`, `HwAg1Meas_PeerReview.xlsm`, `Polyspace`

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

- [HwAg1Meas_IntegrationManual.doc](./hwag1meas-integrationmanual/)
- [HwAg1Meas_MDD.docx](./hwag1meas-mdd/)

## Repository location

Repo path: `CM670A_HwAg1Meas_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
