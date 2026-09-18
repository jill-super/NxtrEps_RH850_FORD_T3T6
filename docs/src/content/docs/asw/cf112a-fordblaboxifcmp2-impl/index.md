---
title: "Ford Black Box Interface Component 2 (CF112A)"
description: "CF112A_FordBlaBoxIfCmp2_Impl: Ford customer-feature SW-C `FordBlaBoxIfCmp2` (CF112A). Implements Ford-specific arbitration, coding or black-box-interface logic on top of platform signals."
---


import { Badge } from '@astrojs/starlight/components';

# Ford Black Box Interface Component 2 (CF112A)

Repo directory: `CF112A_FordBlaBoxIfCmp2_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Ford customer-feature SW-C `FordBlaBoxIfCmp2` (CF112A). Implements Ford-specific arbitration, coding or black-box-interface logic on top of platform signals.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CF112A_FordBlaBoxIfCmp2_Impl/src/CDD_FordBlaBoxIfCmp2.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_FordBlaBoxIfCmp2.c`, `CDD_FordBlaBoxIfCmp2NonRte.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `CDD_FordBlaBoxIfCmp2.dcf`, `CDD_FordBlaBoxIfCmp2_attr_def.xml`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (6 entries): `CF112A_FordBlaBoxIfCmp2_Impl.gpj`, `Component.dpa`, `Component.~lock`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (1 entries): `FordBlaBoxIfCmp2_PeerReviewChecklist.xlsm`

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

- No `.doc`/`.docx`/`.pdf` (or `doc/`-level `.txt`) sources found in this module.

## Repository location

Repo path: `CF112A_FordBlaBoxIfCmp2_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
