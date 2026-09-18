---
title: "Core Voltage Monitor (CM112B)"
description: "CM112B_CoreVltgMonr_Impl: Complex driver `CoreVltgMonr` (CM112B): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# Core Voltage Monitor (CM112B)

Repo directory: `CM112B_CoreVltgMonr_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `CoreVltgMonr` (CM112B): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM112B_CoreVltgMonr_Impl/src/CDD_CoreVltgMonr.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_CoreVltgMonr.c`, `CDD_CoreVltgMonrNonRte.c`
- `include/` (1 entries): `CDD_CoreVltgMonr.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `CoreVltgMonr.dcf`, `CoreVltgMonr_attr_def.xml`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `CM112B_CoreVltgMonr_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `CoreVltgMon_PeerReviewChecklist.xlsm`, `CoreVltgMonr_IntegrationManual.doc`, `CoreVltgMonr_MDD.docx`, `Polyspace`

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

- [CoreVltgMonr_IntegrationManual.doc](./corevltgmonr-integrationmanual/)
- [CoreVltgMonr_MDD.docx](./corevltgmonr-mdd/)

## Repository location

Repo path: `CM112B_CoreVltgMonr_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
