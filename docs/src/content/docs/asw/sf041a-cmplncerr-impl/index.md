---
title: "Compliance Error (SF041A)"
description: "SF041A_CmplncErr_Impl: Application SW-C `CmplncErr` (SF041A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook an"
---


import { Badge } from '@astrojs/starlight/components';

# Compliance Error (SF041A)

Repo directory: `SF041A_CmplncErr_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `CmplncErr` (SF041A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF041A_CmplncErr_Impl/src/CmplncErr.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `CmplncErr.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `CmplncErr.dcf`, `CmplncErr_attr_def.xml`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (12 entries): `CmplncErr.dpa`, `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `Polyspace`, `QAC`, `RteGen.bat`, `SF041A_CmplncErr_Impl.gpj`, `contract`
- `doc/` (6 entries): `CmplncErr_IntegrationManual.doc`, `CmplncErr_MDD.docx`, `CmplncErr_Review.xls`, `Polyspace_Results`, `QAC_Results`, `requirements.csv`

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

- [CmplncErr_IntegrationManual.doc](./cmplncerr-integrationmanual/)
- [CmplncErr_MDD.docx](./cmplncerr-mdd/)

## Repository location

Repo path: `SF041A_CmplncErr_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
