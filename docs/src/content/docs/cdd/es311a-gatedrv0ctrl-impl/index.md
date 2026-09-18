---
title: "Gate Driver 0 Control (ES311A)"
description: "ES311A_GateDrv0Ctrl_Impl: EPS system service `GateDrv0Ctrl` (ES311A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Gate Driver 0 Control (ES311A)

Repo directory: `ES311A_GateDrv0Ctrl_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `GateDrv0Ctrl` (ES311A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES311A_GateDrv0Ctrl_Impl/src/GateDrv0Ctrl.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `GateDrv0Ctrl.c`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `GateDrv0Ctrl.dcf`, `GateDrv0Ctrl_attr_def.xml`, `GateDrv0Ctrl_bswmd.arxml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (7 entries): `Component.dpa`, `ES311A_GateDrv0Ctrl_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`, `template`
- `doc/` (4 entries): `GateDrv0Ctrl_IntegrationManual.doc`, `GateDrv0Ctrl_MDD.doc`, `GateDrv0Ctrl_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [GateDrv0Ctrl_IntegrationManual.doc](./gatedrv0ctrl-integrationmanual/)
- [GateDrv0Ctrl_MDD.doc](./gatedrv0ctrl-mdd/)

## Repository location

Repo path: `ES311A_GateDrv0Ctrl_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
