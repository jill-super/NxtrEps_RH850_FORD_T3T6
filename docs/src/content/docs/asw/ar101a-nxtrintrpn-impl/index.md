---
title: "Nexteer Interpolation (AR101A)"
description: "AR101A_NxtrIntrpn_Impl: Interpolation (table lookup) library shared by control SW-Cs."
---


import { Badge } from '@astrojs/starlight/components';

# Nexteer Interpolation (AR101A)

Repo directory: `AR101A_NxtrIntrpn_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Interpolation (table lookup) library shared by control SW-Cs.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `AR101A_NxtrIntrpn_Impl/src/NxtrIntrpn.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `NxtrIntrpn.c`
- `include/` (2 entries): `NxtrIntrpn.h`, `NxtrIntrpn_MemMap.h`
- `tools/` (4 entries): `AR101A_NxtrIntrpn_Impl.gpj`, `CreateGHSProject.bat`, `Polyspace`, `QAC`
- `doc/` (4 entries): `NxtrIntrpn Integration Manual.doc`, `NxtrIntrpn Review.xlsm`, `Polyspace_Results.zip`, `QAC_Results`

## Generated code and configuration

- No generator/contract folders observed.

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

- [NxtrIntrpn Integration Manual.doc](./nxtrintrpn-integration-manual/)

## Repository location

Repo path: `AR101A_NxtrIntrpn_Impl/` — subfolders present: `src/`, `include/`, `doc/`, `tools/`.
