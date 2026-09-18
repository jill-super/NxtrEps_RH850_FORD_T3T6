---
title: "GTM Configuration and Use (CM770A)"
description: "CM770A_GtmCfgAndUse_Impl: Complex driver `GtmCfgAndUse` (CM770A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# GTM Configuration and Use (CM770A)

Repo directory: `CM770A_GtmCfgAndUse_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `GtmCfgAndUse` (CM770A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM770A_GtmCfgAndUse_Impl/src/CDD_GtmCfgAndUse.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (3 entries): `CDD_GtmCfgAndUse.c`, `CDD_GtmCfgAndUse_MotCtrl.c`, `CDD_GtmCfgAndUse_private.c`
- `include/` (4 entries): `CDD_GtmCfgAndUse.h`, `CDD_GtmCfgAndUseConst_MemMap.h`, `CDD_GtmCfgAndUse_MotCtrl_MemMap.h`, `CDD_GtmCfgAndUse_private.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `GtmCfgAndUse.dcf`, `GtmCfgAndUse_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `CM770A_GtmCfgAndUse_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `GtmCfgAndUse Integration Manual.doc`, `GtmCfgAndUse_MDD.docx`, `GtmCfgAndUse_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [GtmCfgAndUse Integration Manual.doc](./gtmcfganduse-integration-manual/)
- [GtmCfgAndUse_MDD.docx](./gtmcfganduse-mdd/)

## Repository location

Repo path: `CM770A_GtmCfgAndUse_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
