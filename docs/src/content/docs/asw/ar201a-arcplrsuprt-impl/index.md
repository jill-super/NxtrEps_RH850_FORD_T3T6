---
title: "Compiler support types (AR201A)"
description: "AR201A_ArCplrSuprt_Impl: Compiler-abstraction support (Compiler.h / Platform_Types) used across the codebase."
---


import { Badge } from '@astrojs/starlight/components';

# Compiler support types (AR201A)

Repo directory: `AR201A_ArCplrSuprt_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Compiler-abstraction support (Compiler.h / Platform_Types) used across the codebase.

## Origin

**Custom · Nexteer in-house.** No compilable source in this folder (headers/config/tools only); treated as project-owned glue.

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `include/` (1 entries): `ASR4.0.3`
- `tools/` (2 entries): `AR201A_ArCplrSuprt_Impl_ASR4.0.3.gpj`, `contract`
- `doc/` (1 entries): `ArCplrSuprt Peer Review Checklists.xlsm`

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

Repo path: `AR201A_ArCplrSuprt_Impl/` — subfolders present: `include/`, `doc/`, `tools/`.
