---
title: "Motor Ripple Cogging Command (SF107A)"
description: "SF107A_MotRplCoggCmd_Impl: Application SW-C `MotRplCoggCmd` (SF107A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databoo"
---


import { Badge } from '@astrojs/starlight/components';

# Motor Ripple Cogging Command (SF107A)

Repo directory: `SF107A_MotRplCoggCmd_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `MotRplCoggCmd` (SF107A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF107A_MotRplCoggCmd_Impl/src/CDD_MotRplCoggCmd.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_MotRplCoggCmd.c`, `CDD_MotRplCoggCmd_MotCtrl.c`
- `include/` (2 entries): `CDD_MotRplCoggCmd.h`, `CDD_MotRplCoggCmd_MotCtrl_MemMap.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `MotRplCoggCmd.dcf`, `MotRplCoggCmd_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (13 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `DVCfgCmd.log`, `MotRplCoggCmd.dpa`, `Polyspace`, `QAC`, `RteGen.bat`, `SF107A_MotRplCoggCmd_Impl.gpj`, `contract`
- `doc/` (6 entries): `MotRplCoggCmd_IntegrationManual.doc`, `MotRplCoggCmd_MDD.docx`, `MotRplCoggCmd_ReviewChecklists.xlsm`, `Polyspace_Results`, `QAC_Results`, `requirements.csv`

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

- [MotRplCoggCmd_IntegrationManual.doc](./motrplcoggcmd-integrationmanual/)
- [MotRplCoggCmd_MDD.docx](./motrplcoggcmd-mdd/)

## Repository location

Repo path: `SF107A_MotRplCoggCmd_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
