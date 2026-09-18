---
title: "Ford System State (CF052A)"
description: "CF052A_FordSysSt_Impl: Ford customer-feature SW-C `FordSysSt` (CF052A). Implements Ford-specific arbitration, coding or black-box-interface logic on top of platform signals."
---


import { Badge } from '@astrojs/starlight/components';

# Ford System State (CF052A)

Repo directory: `CF052A_FordSysSt_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Ford customer-feature SW-C `FordSysSt` (CF052A). Implements Ford-specific arbitration, coding or black-box-interface logic on top of platform signals.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CF052A_FordSysSt_Impl/src/FordSysSt.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `FordSysSt.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `FordSysSt.dcf`, `FordSysSt_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `CF052A_FordSysSt_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `FordSysSt_IntegrationManual.doc`, `FordSysSt_MDD.docx`, `FordSysSt_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [FordSysSt_IntegrationManual.doc](./fordsysst-integrationmanual/)
- [FordSysSt_MDD.docx](./fordsysst-mdd/)

## Repository location

Repo path: `CF052A_FordSysSt_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
