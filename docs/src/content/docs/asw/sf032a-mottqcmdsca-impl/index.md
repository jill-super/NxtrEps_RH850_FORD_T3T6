---
title: "Motor Torque Command Scaling (SF032A)"
description: "SF032A_MotTqCmdSca_Impl: Application SW-C `MotTqCmdSca` (SF032A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook "
---


import { Badge } from '@astrojs/starlight/components';

# Motor Torque Command Scaling (SF032A)

Repo directory: `SF032A_MotTqCmdSca_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `MotTqCmdSca` (SF032A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF032A_MotTqCmdSca_Impl/src/MotTqCmdSca.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `MotTqCmdSca.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `MotTqCmdSca.dcf`, `MotTqCmdSca_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (12 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `MotTqCmdSca.dpa`, `Polyspace`, `QAC`, `RteGen.bat`, `SF032A_MotTqCmdSca_Impl.gpj`, `contract`
- `doc/` (6 entries): `MotTqCmdSca_IntegrationManual.doc`, `MotTqCmdSca_MDD.docx`, `MotTqCmdSca_Review.xls`, `Polyspace_Results`, `QAC_Results`, `requirements.csv`

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

- [MotTqCmdSca_IntegrationManual.doc](./mottqcmdsca-integrationmanual/)
- [MotTqCmdSca_MDD.docx](./mottqcmdsca-mdd/)

## Repository location

Repo path: `SF032A_MotTqCmdSca_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
