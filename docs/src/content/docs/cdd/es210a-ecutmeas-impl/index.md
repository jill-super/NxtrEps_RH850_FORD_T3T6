---
title: "ECU Temperature Measurement (ES210A)"
description: "ES210A_EcuTMeas_Impl: EPS system service `EcuTMeas` (ES210A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# ECU Temperature Measurement (ES210A)

Repo directory: `ES210A_EcuTMeas_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `EcuTMeas` (ES210A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES210A_EcuTMeas_Impl/src/EcuTMeas.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `EcuTMeas.c`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `EcuTMeas.dcf`, `EcuTMeas_attr_def.xml`, `EcuTMeas_bswmd.arxml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (7 entries): `Component.dpa`, `ES210A_EcuTMeas_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`, `template`
- `doc/` (4 entries): `EcuTMeas_IntegrationManual.doc`, `EcuTMeas_MDD.docx`, `EcuTMeas_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [EcuTMeas_IntegrationManual.doc](./ecutmeas-integrationmanual/)
- [EcuTMeas_MDD.docx](./ecutmeas-mdd/)

## Repository location

Repo path: `ES210A_EcuTMeas_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
