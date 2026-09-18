---
title: "Current Measurement Arbitration (ES208A)"
description: "ES208A_CurrMeasArbn_Impl: EPS system service `CurrMeasArbn` (ES208A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Current Measurement Arbitration (ES208A)

Repo directory: `ES208A_CurrMeasArbn_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `CurrMeasArbn` (ES208A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES208A_CurrMeasArbn_Impl/src/CDD_CurrMeasArbn.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_CurrMeasArbn.c`, `CDD_CurrMeasArbn_MotCtrl.c`
- `include/` (2 entries): `CDD_CurrMeasArbn.h`, `CDD_CurrMeasArbn_MotCtrl_MemMap.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `CurrMeasArbn.dcf`, `CurrMeasArbn_attr_def.xml`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (12 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `CurrMeasArbn.dpa`, `ES208A_CurrMeasArbn_Impl.gpj`, `Polyspace`, `QAC`, `RteGen.bat`, `contract`
- `doc/` (6 entries): `CurrMeasArbn_ Review.xlsm`, `CurrMeasArbn_IntegrationManual.docx`, `CurrMeasArbn_MDD.doc`, `Polyspace_Results.zip`, `QAC_Results`, `requirements.csv`

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

- [CurrMeasArbn_IntegrationManual.docx](./currmeasarbn-integrationmanual/)
- [CurrMeasArbn_MDD.doc](./currmeasarbn-mdd/)

## Repository location

Repo path: `ES208A_CurrMeasArbn_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
