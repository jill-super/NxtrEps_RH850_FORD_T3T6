---
title: "Nexteer Fixed Point (AR103A)"
description: "AR103A_NxtrFixdPt_Impl: Fixed-point helper library shared by control SW-Cs."
---


import { Badge } from '@astrojs/starlight/components';

# Nexteer Fixed Point (AR103A)

Repo directory: `AR103A_NxtrFixdPt_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Fixed-point helper library shared by control SW-Cs.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `AR103A_NxtrFixdPt_Impl/src/NxtrFixdPt.h` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `include/` (1 entries): `NxtrFixdPt.h`
- `tools/` (5 entries): `AR103A_NxtrFixdPt_Impl.gpj`, `CreateGHSProject.bat`, `Polyspace`, `QAC`, `contract`
- `doc/` (4 entries): `NxtrFixdPt Integration Manual.doc`, `NxtrFixdPt Review.xlsm`, `Polyspace_Results.zip`, `QAC_Results`

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

- [NxtrFixdPt Integration Manual.doc](./nxtrfixdpt-integration-manual/)

## Repository location

Repo path: `AR103A_NxtrFixdPt_Impl/` — subfolders present: `include/`, `doc/`, `tools/`.
