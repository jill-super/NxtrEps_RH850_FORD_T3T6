---
title: "Nexteer Software IDs (NM003A)"
description: "NM003A_NxtrSwIds_Impl: Manufacturing/service SW-C `NxtrSwIds` (NM003A): software/part IDs, motor-velocity control support or common MFG services."
---


import { Badge } from '@astrojs/starlight/components';

# Nexteer Software IDs (NM003A)

Repo directory: `NM003A_NxtrSwIds_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Manufacturing/service SW-C `NxtrSwIds` (NM003A): software/part IDs, motor-velocity control support or common MFG services.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `NM003A_NxtrSwIds_Impl/src/NxtrSwIds.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `NxtrSwIds.c`
- `include/` (1 entries): `NxtrSwIds.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `NxtrSwIds.dcf`, `NxtrSwIds_attr_def.xml`, `NxtrSwIds_bswmd.arxml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `generate/` (2 entries): `NxtrSwIdsCfg.c.tt`, `NxtrSwIds_Generate.bat`
- `tools/` (13 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `Integrate.bat`, `IntegrationCopy`, `NM003A_NxtrSwIds_Impl.gpj`, `NxtrSwIds.dpa`, `QAC`, `RteGen.bat`, `UpdateNxtrSwIds.py`, `contract`
- `doc/` (1 entries): `QAC_Results`

## Generated code and configuration

- RTE contracts: `tools/contract/` (input interfaces for this SW-C).
- DaVinci `generate/` output shipped with the module.
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

Repo path: `NM003A_NxtrSwIds_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `generate/`.
