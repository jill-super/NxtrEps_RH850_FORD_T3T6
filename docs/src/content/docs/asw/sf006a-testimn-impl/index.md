---
title: "Torque Estimation (SF006A)"
description: "SF006A_TEstimn_Impl: Application SW-C `TEstimn` (SF006A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and "
---


import { Badge } from '@astrojs/starlight/components';

# Torque Estimation (SF006A)

Repo directory: `SF006A_TEstimn_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `TEstimn` (SF006A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF006A_TEstimn_Impl/src/TEstimn.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `TEstimn.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `TEstimn.dcf`, `TEstimn_attr_def.xml`
- `tools/` (5 entries): `Component.dpa`, `Polyspace`, `SF006A_TEstimn_Impl.gpj`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `Polyspace`, `TEstimn_IntegrationManual.doc`, `TEstimn_MDD.docx`, `TEstimn_Review.xlsm`

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

- [TEstimn_IntegrationManual.doc](./testimn-integrationmanual/)
- [TEstimn_MDD.docx](./testimn-mdd/)

## Repository location

Repo path: `SF006A_TEstimn_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
