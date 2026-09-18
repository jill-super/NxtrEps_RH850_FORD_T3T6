---
title: "Handwheel Torque Correlation (ES229C)"
description: "ES229C_HwTqCorrln_Impl: EPS system service `HwTqCorrln` (ES229C): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Handwheel Torque Correlation (ES229C)

Repo directory: `ES229C_HwTqCorrln_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `HwTqCorrln` (ES229C): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES229C_HwTqCorrln_Impl/src/HwTqCorrln.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `HwTqCorrln.c`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `HwTqCorrln.dcf`, `HwTqCorrln_attr_def.xml`, `HwTqCorrln_bswmd.arxml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (9 entries): `Component.NZ2796.silent.dcusr`, `Component.dpa`, `ES229C_HwTqCorrln_Impl.gpj`, `HwTqCorrln.nz2796.silent.dcusr`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`, `template`
- `doc/` (4 entries): `HwTqCorrln_ Review.xlsm`, `HwTqCorrln_IntegrationManual.doc`, `HwTqCorrln_MDD.docx`, `Polyspace`

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

- [HwTqCorrln_IntegrationManual.doc](./hwtqcorrln-integrationmanual/)
- [HwTqCorrln_MDD.docx](./hwtqcorrln-mdd/)

## Repository location

Repo path: `ES229C_HwTqCorrln_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
