---
title: "Architecture global parameters (AR999A)"
description: "AR999A_ArchGlbPrm_Impl: Architecture global parameters shared across SW-Cs."
---


import { Badge } from '@astrojs/starlight/components';

# Architecture global parameters (AR999A)

Repo directory: `AR999A_ArchGlbPrm_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Architecture global parameters shared across SW-Cs.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `AR999A_ArchGlbPrm_Impl/src/ArchGlbPrm.h` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `include/` (1 entries): `ArchGlbPrm.h`
- `tools/` (5 entries): `AR999A_ArchGlbPrm_Impl.gpj`, `CreateGHSProject.bat`, `Polyspace`, `QAC`, `contract`
- `doc/` (3 entries): `ArchGlbPrm Review.xlsm`, `Polyspace_Results.zip`, `QAC_Results`

## Generated code and configuration

- RTE contracts: `tools/contract/` (input interfaces for this SW-C).

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

Repo path: `AR999A_ArchGlbPrm_Impl/` — subfolders present: `include/`, `doc/`, `tools/`.
