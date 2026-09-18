---
title: "Swp test support (DF002A)"
description: "DF002A_Swp_Impl: Development/test support component `Swp` (DF002A): fault-injection or software-programming hooks used for validation."
---


import { Badge } from '@astrojs/starlight/components';

# Swp test support (DF002A)

Repo directory: `DF002A_Swp_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Development/test support component `Swp` (DF002A): fault-injection or software-programming hooks used for validation.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `DF002A_Swp_Impl/src/Swp.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `Swp.c`
- `include/` (1 entries): `Swp.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `Swp.dcf`, `Swp_attr_def.xml`
- `tools/` (12 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `DF002A_Swp_Impl.gpj`, `Polyspace`, `QAC`, `RteGen.bat`, `Swp.dpa`, `contract`
- `doc/` (5 entries): `Polyspace_Results`, `QAC_Results`, `Swp_DesignReview.xlsm`, `Swp_IntegrationManual.doc`, `Swp_MDD.docx`

## Generated code and configuration

- RTE contracts: `tools/contract/` (input interfaces for this SW-C).
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

- [Swp_IntegrationManual.doc](./swp-integrationmanual/)
- [Swp_MDD.docx](./swp-mdd/)

## Repository location

Repo path: `DF002A_Swp_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
