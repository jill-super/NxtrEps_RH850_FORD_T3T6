---
title: "ADCF 0 Configuration and Use (CM301A)"
description: "CM301A_Adcf0CfgAndUse_Impl: Complex driver `Adcf0CfgAndUse` (CM301A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# ADCF 0 Configuration and Use (CM301A)

Repo directory: `CM301A_Adcf0CfgAndUse_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `Adcf0CfgAndUse` (CM301A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM301A_Adcf0CfgAndUse_Impl/src/CDD_Adcf0CfgAndUse.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_Adcf0CfgAndUse.c`, `CDD_Adcf0CfgAndUse_MotCtrl.c`
- `include/` (2 entries): `CDD_Adcf0CfgAndUse.h`, `CDD_Adcf0CfgAndUse_MotCtrl_MemMap.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `Adcf0CfgAndUse.dcf`, `Adcf0CfgAndUse_attr_def.xml`, `CDD_Adcf0CfgAndUse_bswmd.arxml`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (7 entries): `CM301A_Adcf0CfgAndUse_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`, `template`
- `doc/` (4 entries): `Adcf0CfgAndUse_IntegrationManual.docx`, `Adcf0CfgAndUse_MDD.docx`, `Adcf0CfgAndUse_Review.xlsm`, `Polyspace`

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

- [Adcf0CfgAndUse_IntegrationManual.docx](./adcf0cfganduse-integrationmanual/)
- [Adcf0CfgAndUse_MDD.docx](./adcf0cfganduse-mdd/)

## Repository location

Repo path: `CM301A_Adcf0CfgAndUse_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
