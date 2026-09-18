---
title: "System global parameters (SF999A)"
description: "SF999A_SysGlbPrm_Impl: Application SW-C `SysGlbPrm` (SF999A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook an"
---


import { Badge } from '@astrojs/starlight/components';

# System global parameters (SF999A)

Repo directory: `SF999A_SysGlbPrm_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `SysGlbPrm` (SF999A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF999A_SysGlbPrm_Impl/src/SysGlbPrm.h` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `include/` (1 entries): `SysGlbPrm.h`
- `tools/` (10 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `Polyspace`, `QAC`, `RteGen.bat`, `SF999A_SysGlbPrm_Impl.gpj`, `SysGlbPrm.dpa`, `contract`
- `doc/` (3 entries): `Polyspace_Results`, `QAC_Results`, `SysGlbPrm Review.xlsm`

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

Repo path: `SF999A_SysGlbPrm_Impl/` — subfolders present: `include/`, `doc/`, `tools/`.
