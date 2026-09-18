---
title: "Electrical global parameters (ES999A)"
description: "ES999A_ElecGlbPrm_Impl: EPS system service `ElecGlbPrm` (ES999A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Electrical global parameters (ES999A)

Repo directory: `ES999A_ElecGlbPrm_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `ElecGlbPrm` (ES999A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES999A_ElecGlbPrm_Impl/src/ElecGlbPrm.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `ElecGlbPrm.c`
- `include/` (2 entries): `ElecGlbPrm.h`, `ElecGlbPrm_MemMap.h`
- `autosar/` (1 entries): `ElecGlbPrm_bswmd.arxml`
- `tools/` (7 entries): `Component.dpa`, `ES999A_ElecGlbPrm_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`, `template`
- `doc/` (3 entries): `ElecGlbPrm Review.xlsm`, `ElecGlbPrm_IntegrationManual.doc`, `Polyspace`

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

- [ElecGlbPrm_IntegrationManual.doc](./elecglbprm-integrationmanual/)

## Repository location

Repo path: `ES999A_ElecGlbPrm_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
