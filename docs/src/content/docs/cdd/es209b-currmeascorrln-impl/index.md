---
title: "Current Measurement Correlation (ES209B)"
description: "ES209B_CurrMeasCorrln_Impl: EPS system service `CurrMeasCorrln` (ES209B): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Current Measurement Correlation (ES209B)

Repo directory: `ES209B_CurrMeasCorrln_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `CurrMeasCorrln` (ES209B): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES209B_CurrMeasCorrln_Impl/src/CurrMeasCorrln.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `CurrMeasCorrln.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `CurrMeasCorrln.dcf`, `CurrMeasCorrln_attr_def.xml`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `Component.dpa`, `ES209B_CurrMeasCorrln_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `CurrMeasCorrln_IntegrationManual.docx`, `CurrMeasCorrln_MDD.docx`, `CurrMeasCorrln_PeerReview.xlsm`, `Polyspace`

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

- [CurrMeasCorrln_IntegrationManual.docx](./currmeascorrln-integrationmanual/)
- [CurrMeasCorrln_MDD.docx](./currmeascorrln-mdd/)

## Repository location

Repo path: `ES209B_CurrMeasCorrln_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
