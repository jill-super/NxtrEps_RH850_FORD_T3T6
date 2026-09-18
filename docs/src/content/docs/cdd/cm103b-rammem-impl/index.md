---
title: "RAM memory (CM103B)"
description: "CM103B_RamMem_Impl: Complex driver `RamMem` (CM103B): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# RAM memory (CM103B)

Repo directory: `CM103B_RamMem_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `RamMem` (CM103B): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM103B_RamMem_Impl/src/CDD_RamMem.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_RamMem.c`, `CDD_RamMemNonRte.c`
- `include/` (1 entries): `CDD_RamMem.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `RamMem.dcf`, `RamMem_attr_def.xml`
- `tools/` (5 entries): `CM103B_RamMem_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `Polyspace`, `RamMem_IntegrationManual.doc`, `RamMem_MDD.docx`, `RamMem_PeerReviewChecklist.xlsm`

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

- [RamMem_IntegrationManual.doc](./rammem-integrationmanual/)
- [RamMem_MDD.docx](./rammem-mdd/)

## Repository location

Repo path: `CM103B_RamMem_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
