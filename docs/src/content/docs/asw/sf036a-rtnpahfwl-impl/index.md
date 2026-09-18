---
title: "Return Path Firewall (SF036A)"
description: "SF036A_RtnPahFwl_Impl: Application SW-C `RtnPahFwl` (SF036A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook an"
---


import { Badge } from '@astrojs/starlight/components';

# Return Path Firewall (SF036A)

Repo directory: `SF036A_RtnPahFwl_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `RtnPahFwl` (SF036A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF036A_RtnPahFwl_Impl/src/RtnPahFwl.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `RtnPahFwl.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `RtnPahFwl.dcf`, `RtnPahFwl_attr_def.xml`
- `tools/` (12 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `Polyspace`, `QAC`, `RteGen.bat`, `RtnPahFwl.dpa`, `SF036A_RtnPahFwl_Impl.gpj`, `contract`
- `doc/` (5 entries): `Polyspace_Results`, `QAC_Results`, `RtnPahFwl_IntegrationManual.doc`, `RtnPahFwl_MDD.doc`, `RtnPahFwl_Review.xls`

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

- [RtnPahFwl_IntegrationManual.doc](./rtnpahfwl-integrationmanual/)
- [RtnPahFwl_MDD.doc](./rtnpahfwl-mdd/)

## Repository location

Repo path: `SF036A_RtnPahFwl_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
