---
title: "Nexteer Startup (AR400A)"
description: "AR400A_NxtrStrtUp_Impl: Startup library: early initialisation helpers before the OS/RTE is up."
---


import { Badge } from '@astrojs/starlight/components';

# Nexteer Startup (AR400A)

Repo directory: `AR400A_NxtrStrtUp_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Startup library: early initialisation helpers before the OS/RTE is up.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `AR400A_NxtrStrtUp_Impl/src/NxtrStrtUp.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `NxtrStrtUp.c`, `NxtrStrtUpLo.850`
- `include/` (1 entries): `NxtrStrtUp.h`
- `tools/` (4 entries): `AR400A_NxtrStrtUp_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (3 entries): `NxtrStrtUp_IntegrationManual.docx`, `NxtrStrtUp_PeerReviewChecklist.xlsm`, `Polyspace`

## Generated code and configuration

- Local generation output: `tools/local/generate/`.

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

- [NxtrStrtUp_IntegrationManual.docx](./nxtrstrtup-integrationmanual/)

## Repository location

Repo path: `AR400A_NxtrStrtUp_Impl/` — subfolders present: `src/`, `include/`, `doc/`, `tools/`.
