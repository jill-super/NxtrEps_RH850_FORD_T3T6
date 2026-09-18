---
title: "DMA Configuration and Use (CM201A)"
description: "CM201A_DmaCfgAndUse_Impl: Complex driver `DmaCfgAndUse` (CM201A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# DMA Configuration and Use (CM201A)

Repo directory: `CM201A_DmaCfgAndUse_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `DmaCfgAndUse` (CM201A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM201A_DmaCfgAndUse_Impl/src/CDD_DmaCfgAndUse.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `CDD_DmaCfgAndUse.c`
- `include/` (1 entries): `CDD_DmaCfgAndUse.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `DmaCfgAndUse.dcf`, `DmaCfgAndUse_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `CM201A_DmaCfgAndUse_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `DmaCfgAndUse_IntegrationManual.doc`, `DmaCfgAndUse_MDD.docx`, `DmaCfgAndUse_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [DmaCfgAndUse_IntegrationManual.doc](./dmacfganduse-integrationmanual/)
- [DmaCfgAndUse_MDD.docx](./dmacfganduse-mdd/)

## Repository location

Repo path: `CM201A_DmaCfgAndUse_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
