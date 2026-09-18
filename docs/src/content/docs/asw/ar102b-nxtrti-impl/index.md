---
title: "Nexteer Time (AR102B)"
description: "AR102B_NxtrTi_Impl: Time-base utilities shared by control SW-Cs."
---


import { Badge } from '@astrojs/starlight/components';

# Nexteer Time (AR102B)

Repo directory: `AR102B_NxtrTi_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Time-base utilities shared by control SW-Cs.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `AR102B_NxtrTi_Impl/src/CDD_NxtrTi.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `CDD_NxtrTi.c`
- `include/` (1 entries): `CDD_NxtrTi.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `NxtrTi.dcf`, `NxtrTi_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (6 entries): `AR102B_NxtrTi_Impl.gpj`, `Component.KZDYFH.silent.dcusr`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (3 entries): `NxtrTi Integration Manual.doc`, `NxtrTi Review.xlsm`, `Polyspace`

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

- [NxtrTi Integration Manual.doc](./nxtrti-integration-manual/)

## Repository location

Repo path: `AR102B_NxtrTi_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
