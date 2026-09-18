---
title: "NVRAM proxy service (ES006A)"
description: "ES006A_NvM_Impl: EPS system service `NvM` (ES006A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# NVRAM proxy service (ES006A)

Repo directory: `ES006A_NvM_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `NvM` (ES006A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES006A_NvM_Impl/src/CDD_NvMProxy.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (3 entries): `CDD_NvMProxy.c`, `CDD_NvMProxyApi.c`, `CDD_NvMProxyNonRte.c`
- `include/` (1 entries): `CDD_NvMProxy.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `NvMProxy.dcf`, `NvMProxy_attr_def.xml`, `NvMProxy_bswmd.arxml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `generate/` (8 entries): `CDD_NvMProxyDftDataGroup.h.tt`, `CDD_NvMProxy_Cbk.c.tt`, `CDD_NvMProxy_Cbk.h.tt`, `CDD_NvMProxy_Cfg.c.tt`, `CDD_NvMProxy_Cfg.h.tt`, `CDD_NvMProxy_Cfg_private.h.tt`, `NvMProxy_Generate.bat`, `NvMProxy_swc.arxml.tt`
- `tools/` (13 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `DVCfgCmd.log`, `ES006A_NvM_Impl.gpj`, `Integrate.bat`, `IntegrationCopy`, `NvMProxy.dpa`, `Polyspace`, `QAC`, `RteGen.bat`, `contract`
- `doc/` (4 entries): `ES006A_NvM_Integration_Manual.doc`, `NvMProxy Review.xlsm`, `Polyspace_Results`, `QAC_Results`

## Generated code and configuration

- RTE contracts: `tools/contract/` (input interfaces for this SW-C).
- DaVinci `generate/` output shipped with the module.
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

- [ES006A_NvM_Integration_Manual.doc](./es006a-nvm-integration-manual/)

## Repository location

Repo path: `ES006A_NvM_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `generate/`.
