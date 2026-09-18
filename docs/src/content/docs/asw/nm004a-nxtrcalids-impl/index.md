---
title: "Nexteer Calibration IDs (NM004A)"
description: "NM004A_NxtrCalIds_Impl: Manufacturing/service SW-C `NxtrCalIds` (NM004A): software/part IDs, motor-velocity control support or common MFG services."
---


import { Badge } from '@astrojs/starlight/components';

# Nexteer Calibration IDs (NM004A)

Repo directory: `NM004A_NxtrCalIds_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Manufacturing/service SW-C `NxtrCalIds` (NM004A): software/part IDs, motor-velocity control support or common MFG services.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `NM004A_NxtrCalIds_Impl/src/NxtrCalIds.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `NxtrCalIds.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `NxtrCalIds.dcf`, `NxtrCalIds_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (11 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `NM004A_NxtrCalIds_Impl.gpj`, `NxtrCalIds.dpa`, `QAC`, `RteGen.bat`, `contract`
- `doc/` (2 entries): `NM004A_NxtrCalIds_DataDict.m`, `QAC_Results`

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

- No `.doc`/`.docx`/`.pdf` (or `doc/`-level `.txt`) sources found in this module.

## Repository location

Repo path: `NM004A_NxtrCalIds_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
