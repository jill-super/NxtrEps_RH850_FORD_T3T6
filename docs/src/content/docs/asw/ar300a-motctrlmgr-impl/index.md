---
title: "Motor Control Manager (AR300A)"
description: "AR300A_MotCtrlMgr_Impl: Motor-control manager: shared scheduling/coordination for the motor-control feature cluster."
---


import { Badge } from '@astrojs/starlight/components';

# Motor Control Manager (AR300A)

Repo directory: `AR300A_MotCtrlMgr_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Motor-control manager: shared scheduling/coordination for the motor-control feature cluster.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `AR300A_MotCtrlMgr_Impl/src/CDD_MotCtrlMgr_Irq.h` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `include/` (2 entries): `CDD_MotCtrlMgr_Irq.h`, `MotCtrlMgr_MemMap.h`
- `autosar/` (1 entries): `CDD_MotCtrlMgr_bswmd.arxml`
- `tools/` (7 entries): `AR300A_MotCtrlMgr_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`, `template`
- `doc/` (4 entries): `MotCtrlMgr Integration Manual.doc`, `MotCtrlMgr Review.xlsm`, `MotCtrlMgr_MDD.doc`, `Polyspace`

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

- [MotCtrlMgr Integration Manual.doc](./motctrlmgr-integration-manual/)
- [MotCtrlMgr_MDD.doc](./motctrlmgr-mdd/)
- [MotCtrlMgr DataDictionary Tool User Guide.docx](./motctrlmgr-datadictionary-tool-user-guide/)

## Repository location

Repo path: `AR300A_MotCtrlMgr_Impl/` — subfolders present: `include/`, `autosar/`, `doc/`, `tools/`.
