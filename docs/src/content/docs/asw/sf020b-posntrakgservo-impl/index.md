---
title: "Position Tracking Servo (SF020B)"
description: "SF020B_PosnTrakgServo_Impl: Application SW-C `PosnTrakgServo` (SF020B steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databo"
---


import { Badge } from '@astrojs/starlight/components';

# Position Tracking Servo (SF020B)

Repo directory: `SF020B_PosnTrakgServo_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `PosnTrakgServo` (SF020B steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF020B_PosnTrakgServo_Impl/src/PosnTrakgServo.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `PosnTrakgServo.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `PosnTrakgServo.dcf`, `PosnTrakgServo_attr_def.xml`, `ProfileSettings.xml`
- `tools/` (12 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `Polyspace`, `PosnTrakgServo.dpa`, `QAC`, `RteGen.bat`, `SF020B_PosnTrakgServo_Impl.gpj`, `contract`
- `doc/` (5 entries): `Polyspace_Results`, `PosnTrakgServo_IntegrationManual.doc`, `PosnTrakgServo_MDD.docx`, `PosnTrakgServo_Review.xlsm`, `QAC_Results`

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

- [PosnTrakgServo_IntegrationManual.doc](./posntrakgservo-integrationmanual/)
- [PosnTrakgServo_MDD.docx](./posntrakgservo-mdd/)

## Repository location

Repo path: `SF020B_PosnTrakgServo_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
