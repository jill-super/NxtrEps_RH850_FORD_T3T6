---
title: "ADCF 1 Configuration and Use (CM321A)"
description: "CM321A_Adcf1CfgAndUse_Impl: Complex driver `Adcf1CfgAndUse` (CM321A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# ADCF 1 Configuration and Use (CM321A)

Repo directory: `CM321A_Adcf1CfgAndUse_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `Adcf1CfgAndUse` (CM321A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM321A_Adcf1CfgAndUse_Impl/src/Adcf1CfgAndUse.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `Adcf1CfgAndUse.c`
- `include/` (1 entries): `Adcf1CfgAndUse.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `Adcf1CfgAndUse.dcf`, `Adcf1CfgAndUse_attr_def.xml`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (6 entries): `CM321A_Adcf1CfgAndUse_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `local`, `template`
- `doc/` (4 entries): `Adcf1CfgAndUse_IntegrationManual.docx`, `Adcf1CfgAndUse_MDD.docx`, `CM321A_Adcf1CfgAndUse Peer Review Checklists.xlsm`, `Polyspace`

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

- [Adcf1CfgAndUse_IntegrationManual.docx](./adcf1cfganduse-integrationmanual/)
- [Adcf1CfgAndUse_MDD.docx](./adcf1cfganduse-mdd/)

## Repository location

Repo path: `CM321A_Adcf1CfgAndUse_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
