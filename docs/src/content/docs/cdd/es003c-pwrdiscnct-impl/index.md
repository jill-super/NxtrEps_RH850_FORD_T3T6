---
title: "Power Disconnect (ES003C)"
description: "ES003C_PwrDiscnct_Impl: EPS system service `PwrDiscnct` (ES003C): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Power Disconnect (ES003C)

Repo directory: `ES003C_PwrDiscnct_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `PwrDiscnct` (ES003C): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES003C_PwrDiscnct_Impl/src/PwrDiscnct.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `PwrDiscnct.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `PwrDiscnct.dcf`, `PwrDiscnct_attr_def.xml`
- `tools/` (5 entries): `Component.dpa`, `ES003C_PwrDiscnct_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `Polyspace`, `PwrDiscnct_IntegrationManual.doc`, `PwrDiscnct_MDD.doc`, `PwrDiscnct_PeerReviewChecklist.xlsm`

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

- [PwrDiscnct_IntegrationManual.doc](./pwrdiscnct-integrationmanual/)
- [PwrDiscnct_MDD.doc](./pwrdiscnct-mdd/)

## Repository location

Repo path: `ES003C_PwrDiscnct_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
