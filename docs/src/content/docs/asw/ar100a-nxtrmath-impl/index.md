---
title: "Nexteer Math Library (AR100A)"
description: "AR100A_NxtrMath_Impl: Fixed-point math library (incl. optimised SinCos) shared by control SW-Cs."
---


import { Badge } from '@astrojs/starlight/components';

# Nexteer Math Library (AR100A)

Repo directory: `AR100A_NxtrMath_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Fixed-point math library (incl. optimised SinCos) shared by control SW-Cs.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `AR100A_NxtrMath_Impl/src/NxtrMath.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `NxtrMath.c`, `NxtrMathNonRte.c`
- `include/` (2 entries): `NxtrMath.h`, `NxtrMath_private.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `NxtrMath.dcf`, `NxtrMath_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `AR100A_NxtrMath_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (5 entries): `NxtrMath Integration Manual.doc`, `NxtrMath Review.xlsm`, `Optimized SinCos Algorithm Rev 001.docx`, `Polyspace`, `SinCos_f32()_Simulation.xlsx`

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

- [NxtrMath Integration Manual.doc](./nxtrmath-integration-manual/)
- [Optimized SinCos Algorithm Rev 001.docx](./optimized-sincos-algorithm-rev-001/)

## Repository location

Repo path: `AR100A_NxtrMath_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
