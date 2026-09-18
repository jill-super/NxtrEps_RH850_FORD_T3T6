---
title: "UART 0 Configuration and Use (CM760A)"
description: "CM760A_Uart0CfgAndUse_Impl: Complex driver `Uart0CfgAndUse` (CM760A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# UART 0 Configuration and Use (CM760A)

Repo directory: `CM760A_Uart0CfgAndUse_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `Uart0CfgAndUse` (CM760A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM760A_Uart0CfgAndUse_Impl/src/CDD_Uart0CfgAndUse.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `CDD_Uart0CfgAndUse.c`
- `include/` (3 entries): `CDD_Uart0CfgAndUse.h`, `CDD_Uart0CfgAndUseNonRte_MemMap.h`, `CDD_Uart0CfgAndUse_private.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `Uart0CfgAndUse.dcf`, `Uart0CfgAndUse_attr_def.xml`
- `tools/` (5 entries): `CM760A_Uart0CfgAndUse_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `Polyspace`, `Uart0CfgAndUse_IntegrationManual.doc`, `Uart0CfgAndUse_MDD.docx`, `Uart0CfgAndUse_PeerReviewChecklist.xlsm`

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

- [Uart0CfgAndUse_IntegrationManual.doc](./uart0cfganduse-integrationmanual/)
- [Uart0CfgAndUse_MDD.docx](./uart0cfganduse-mdd/)

## Repository location

Repo path: `CM760A_Uart0CfgAndUse_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
