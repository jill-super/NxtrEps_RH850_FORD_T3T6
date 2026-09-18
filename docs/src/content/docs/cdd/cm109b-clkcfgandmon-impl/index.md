---
title: "Clock Configuration and Monitor (CM109B)"
description: "CM109B_ClkCfgAndMon_Impl: Complex driver `ClkCfgAndMon` (CM109B): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# Clock Configuration and Monitor (CM109B)

Repo directory: `CM109B_ClkCfgAndMon_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `ClkCfgAndMon` (CM109B): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM109B_ClkCfgAndMon_Impl/src/CDD_ClkCfgAndMon.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_ClkCfgAndMon.c`, `CDD_ClkCfgAndMonNonRte.c`
- `include/` (1 entries): `CDD_ClkCfgAndMon.h`
- `autosar/` (7 entries): `AUTOSAR_4-0-3.xsd`, `ClkCfgAndMon.dcf`, `ClkCfgAndMon_attr_def.xml`, `ComponentTypes`, `Packages.arxml`, `Packages_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `CM109B_ClkCfgAndMon_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `ClkCfgAndMon_IntegrationManual.doc`, `ClkCfgAndMon_MDD.docx`, `ClkCfgAndMon_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [ClkCfgAndMon_IntegrationManual.doc](./clkcfgandmon-integrationmanual/)
- [ClkCfgAndMon_MDD.docx](./clkcfgandmon-mdd/)

## Repository location

Repo path: `CM109B_ClkCfgAndMon_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
