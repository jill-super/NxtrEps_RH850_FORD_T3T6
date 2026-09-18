---
title: "MCU Core Configuration and Diagnostics (CM106B)"
description: "CM106B_McuCoreCfgAndDiagc_Impl: Complex driver `McuCoreCfgAndDiagc` (CM106B): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# MCU Core Configuration and Diagnostics (CM106B)

Repo directory: `CM106B_McuCoreCfgAndDiagc_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `McuCoreCfgAndDiagc` (CM106B): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM106B_McuCoreCfgAndDiagc_Impl/src/CDD_McuCoreCfgAndDiagc.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_McuCoreCfgAndDiagc.c`, `CDD_McuCoreCfgAndDiagcNonRte.c`
- `include/` (1 entries): `CDD_McuCoreCfgAndDiagc.h`
- `autosar/` (9 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `McuCoreCfgAndDiagc.dcf`, `McuCoreCfgAndDiagc_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `CM106B_McuCoreCfgAndDiagc_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `McuCoreCfgAndDiagc_IntegrationManual.doc`, `McuCoreCfgAndDiagc_MDD.docx`, `McuCoreCfgAndDiagc_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [McuCoreCfgAndDiagc_IntegrationManual.doc](./mcucorecfganddiagc-integrationmanual/)
- [McuCoreCfgAndDiagc_MDD.docx](./mcucorecfganddiagc-mdd/)

## Repository location

Repo path: `CM106B_McuCoreCfgAndDiagc_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
