---
title: "Current Measurement (ES200B)"
description: "ES200B_CurrMeas_Impl: EPS system service `CurrMeas` (ES200B): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Current Measurement (ES200B)

Repo directory: `ES200B_CurrMeas_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `CurrMeas` (ES200B): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES200B_CurrMeas_Impl/src/CDD_CurrMeas.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_CurrMeas.c`, `CDD_CurrMeas_MotCtrl.c`
- `include/` (2 entries): `CDD_CurrMeas.h`, `CDD_CurrMeas_MotCtrl_MemMap.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `CurrMeas.dcf`, `CurrMeas_attr_def.xml`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `Component.dpa`, `ES200B_CurrMeas_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `CurrMeas_IntegrationManual.doc`, `CurrMeas_MDD.docx`, `CurrMeas_Review.xlsm`, `Polyspace`

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

- [CurrMeas_IntegrationManual.doc](./currmeas-integrationmanual/)
- [CurrMeas_MDD.docx](./currmeas-mdd/)

## Repository location

Repo path: `ES200B_CurrMeas_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
