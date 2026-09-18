---
title: "Handwheel Angle Arbitration (ES238B)"
description: "ES238B_HwAgArbn_Impl: EPS system service `HwAgArbn` (ES238B): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Handwheel Angle Arbitration (ES238B)

Repo directory: `ES238B_HwAgArbn_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `HwAgArbn` (ES238B): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES238B_HwAgArbn_Impl/src/HwAgArbn.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `HwAgArbn.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `HwAgArbn.dcf`, `HwAgArbn_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (12 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `ES238B_HwAgArbn_Impl.gpj`, `HwAgArbn.dpa`, `Polyspace`, `QAC`, `RteGen.bat`, `contract`
- `doc/` (5 entries): `HwAgArbn_DesignReview.xlsm`, `HwAgArbn_IntegrationManual.doc`, `HwAgArbn_MDD.docx`, `Polyspace_Results`, `QAC_Results`

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

- [HwAgArbn_IntegrationManual.doc](./hwagarbn-integrationmanual/)
- [HwAgArbn_MDD.docx](./hwagarbn-mdd/)

## Repository location

Repo path: `ES238B_HwAgArbn_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
