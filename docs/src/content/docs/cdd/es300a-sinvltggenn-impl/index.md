---
title: "Sine Voltage Generation (ES300A)"
description: "ES300A_SinVltgGenn_Impl: EPS system service `SinVltgGenn` (ES300A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Sine Voltage Generation (ES300A)

Repo directory: `ES300A_SinVltgGenn_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `SinVltgGenn` (ES300A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES300A_SinVltgGenn_Impl/src/CDD_SinVltgGenn.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_SinVltgGenn.c`, `CDD_SinVltgGenn_MotCtrl.c`
- `include/` (3 entries): `CDD_SinVltgGenn.h`, `CDD_SinVltgGenn_MotCtrl_MemMap.h`, `CDD_SinVltgGenn_private.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `SinVltgGenn.dcf`, `SinVltgGenn_attr_def.xml`
- `tools/` (5 entries): `Component.dpa`, `ES300A_SinVltgGenn_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `Polyspace`, `SinVltgGenn_IntegrationManual.doc`, `SinVltgGenn_MDD.doc`, `SinVltgGenn_Review.xlsm`

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

- [SinVltgGenn_IntegrationManual.doc](./sinvltggenn-integrationmanual/)
- [SinVltgGenn_MDD.doc](./sinvltggenn-mdd/)

## Repository location

Repo path: `ES300A_SinVltgGenn_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
