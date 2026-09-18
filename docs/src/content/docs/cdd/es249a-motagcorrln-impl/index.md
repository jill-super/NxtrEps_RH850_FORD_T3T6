---
title: "Motor Angle Correlation (ES249A)"
description: "ES249A_MotAgCorrln_Impl: EPS system service `MotAgCorrln` (ES249A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Motor Angle Correlation (ES249A)

Repo directory: `ES249A_MotAgCorrln_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `MotAgCorrln` (ES249A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES249A_MotAgCorrln_Impl/src/MotAgCorrln.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `MotAgCorrln.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `MotAgCorrln.dcf`, `MotAgCorrln_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (12 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `ES249A_MotAgCorrln_Impl.gpj`, `MotAgCorrln.dpa`, `Polyspace`, `QAC`, `RteGen.bat`, `contract`
- `doc/` (6 entries): `MotAgCorrln_DesignReview.xlsm`, `MotAgCorrln_Integration Manual.docx`, `MotAgCorrln_MDD.docx`, `Polyspace_Results`, `QAC_Results`, `requirements.csv`

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

- [MotAgCorrln_Integration Manual.docx](./motagcorrln-integration-manual/)
- [MotAgCorrln_MDD.docx](./motagcorrln-mdd/)

## Repository location

Repo path: `ES249A_MotAgCorrln_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
