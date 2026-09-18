---
title: "Flash Memory (CM102B)"
description: "CM102B_FlsMem_Impl: Complex driver `FlsMem` (CM102B): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# Flash Memory (CM102B)

Repo directory: `CM102B_FlsMem_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `FlsMem` (CM102B): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM102B_FlsMem_Impl/src/CDD_FlsMem.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_FlsMem.c`, `CDD_FlsMemNonRte.c`
- `include/` (3 entries): `CDD_FlsMem.h`, `CDD_FlsMemNonRte_MemMap.h`, `NxtrDtsCh_RegDefns.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `FlsMem.dcf`, `FlsMem_attr_def.xml`, `FlsMem_bswmd.arxml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (7 entries): `CM102B_FlsMem_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`, `template`
- `doc/` (4 entries): `FlsMem Integration Manual.doc`, `FlsMem Module Design Document.docx`, `FlsMem Peer Review Checklists.xlsm`, `Polyspace`

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

- [FlsMem Integration Manual.doc](./flsmem-integration-manual/)
- [FlsMem Module Design Document.docx](./flsmem-module-design-document/)

## Repository location

Repo path: `CM102B_FlsMem_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
