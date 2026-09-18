---
title: "Ford Black Box Interface Component 1 (CF111A)"
description: "CF111A_FordBlaBoxIfCmp1_Impl: Ford customer-feature SW-C `FordBlaBoxIfCmp1` (CF111A). Implements Ford-specific arbitration, coding or black-box-interface logic on top of platform signals."
---


import { Badge } from '@astrojs/starlight/components';

# Ford Black Box Interface Component 1 (CF111A)

Repo directory: `CF111A_FordBlaBoxIfCmp1_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Ford customer-feature SW-C `FordBlaBoxIfCmp1` (CF111A). Implements Ford-specific arbitration, coding or black-box-interface logic on top of platform signals.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CF111A_FordBlaBoxIfCmp1_Impl/src/CDD_FordBlaBoxIfCmp1.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_FordBlaBoxIfCmp1.c`, `CDD_FordBlaBoxIfCmp1NonRte.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `CDD_FordBlaBoxIfCmp1.dcf`, `CDD_FordBlaBoxIfCmp1_attr_def.xml`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `CF111A_FordBlaBoxIfCmp1_Impl.gpj`, `Component.NZ2728.silent.dcusr`, `Component.dpa`, `SWCSupport.bat`, `local`
- `doc/` (1 entries): `FordBlaBoxIfCmp1_PeerReviewChecklist.xlsm`

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

Repo path: `CF111A_FordBlaBoxIfCmp1_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
