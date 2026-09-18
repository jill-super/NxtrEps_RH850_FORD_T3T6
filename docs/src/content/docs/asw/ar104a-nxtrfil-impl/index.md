---
title: "Nexteer Filter (AR104A)"
description: "AR104A_NxtrFil_Impl: Filtering library (low-pass etc.) shared by control SW-Cs."
---


import { Badge } from '@astrojs/starlight/components';

# Nexteer Filter (AR104A)

Repo directory: `AR104A_NxtrFil_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Filtering library (low-pass etc.) shared by control SW-Cs.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `AR104A_NxtrFil_Impl/src/NxtrFil.h` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `include/` (1 entries): `NxtrFil.h`
- `tools/` (5 entries): `AR104A_NxtrFil_Impl.gpj`, `CreateGHSProject.bat`, `Polyspace`, `QAC`, `contract`
- `doc/` (4 entries): `NxtrFil Integration Manual.doc`, `NxtrFil Review.xlsm`, `Polyspace_Results.zip`, `QAC_Results`

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

- [NxtrFil Integration Manual.doc](./nxtrfil-integration-manual/)

## Repository location

Repo path: `AR104A_NxtrFil_Impl/` — subfolders present: `include/`, `doc/`, `tools/`.
