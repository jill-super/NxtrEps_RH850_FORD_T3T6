---
title: "Ford Black Box Interface Common (CF110A)"
description: "CF110A_FordBlaBoxIfCmn_Impl: Ford customer-feature SW-C `FordBlaBoxIfCmn` (CF110A). Implements Ford-specific arbitration, coding or black-box-interface logic on top of platform signals."
---


import { Badge } from '@astrojs/starlight/components';

# Ford Black Box Interface Common (CF110A)

Repo directory: `CF110A_FordBlaBoxIfCmn_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Ford customer-feature SW-C `FordBlaBoxIfCmn` (CF110A). Implements Ford-specific arbitration, coding or black-box-interface logic on top of platform signals.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CF110A_FordBlaBoxIfCmn_Impl/src/CDD_FordBlaBoxIfCmn.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_FordBlaBoxIfCmn.c`, `CDD_FordBlaBoxIfCmnNonRte.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `CDD_FordBlaBoxIfCmn.dcf`, `CDD_FordBlaBoxIfCmn_attr_def.xml`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (4 entries): `CF110A_FordBlaBoxIfCmn_Impl.gpj`, `Component.dpa`, `Component.nz2610.silent.dcusr`, `local`
- `doc/` (1 entries): `FordBlaBoxIfCmn_PeerReviewChecklist.xlsm`

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

Repo path: `CF110A_FordBlaBoxIfCmn_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
