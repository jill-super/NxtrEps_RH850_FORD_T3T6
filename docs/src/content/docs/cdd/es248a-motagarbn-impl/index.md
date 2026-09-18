---
title: "Motor Angle Arbitration (ES248A)"
description: "ES248A_MotAgArbn_Impl: EPS system service `MotAgArbn` (ES248A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Motor Angle Arbitration (ES248A)

Repo directory: `ES248A_MotAgArbn_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `MotAgArbn` (ES248A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES248A_MotAgArbn_Impl/src/CDD_MotAgArbn.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_MotAgArbn.c`, `CDD_MotAgArbn_MotCtrl.c`
- `include/` (2 entries): `CDD_MotAgArbn.h`, `CDD_MotAgArbn_MotCtrl_MemMap.h`
- `autosar/` (9 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `MotAgArbn.dcf`, `MotAgArbn_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `Component.dpa`, `ES248A_MotAgArbn_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `MotAgArbn_IntegrationManual.doc`, `MotAgArbn_MDD.docx`, `MotAgArbn_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [MotAgArbn_IntegrationManual.doc](./motagarbn-integrationmanual/)
- [MotAgArbn_MDD.docx](./motagarbn-mdd/)

## Repository location

Repo path: `ES248A_MotAgArbn_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
