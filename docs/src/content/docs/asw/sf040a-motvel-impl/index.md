---
title: "Motor Velocity (SF040A)"
description: "SF040A_MotVel_Impl: Application SW-C `MotVel` (SF040A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and v"
---


import { Badge } from '@astrojs/starlight/components';

# Motor Velocity (SF040A)

Repo directory: `SF040A_MotVel_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `MotVel` (SF040A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF040A_MotVel_Impl/src/CDD_MotVel.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_MotVel.c`, `CDD_MotVel_MotCtrl.c`
- `include/` (3 entries): `CDD_MotVel.h`, `CDD_MotVel_MotCtrl_MemMap.h`, `CDD_MotVel_private.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `MotVel.dcf`, `MotVel_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (6 entries): `Component.dpa`, `Component.nz3541.silent.dcusr`, `Polyspace`, `SF040A_MotVel_Impl.gpj`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `MotVel_Integration Manual.docx`, `MotVel_MDD.docx`, `MotVel_Peer Review Checklist.xlsm`, `Polyspace`

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

- [MotVel_Integration Manual.docx](./motvel-integration-manual/)
- [MotVel_MDD.docx](./motvel-mdd/)

## Repository location

Repo path: `SF040A_MotVel_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
