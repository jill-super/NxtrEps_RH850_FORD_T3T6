---
title: "Tuning Selection Management (ES400A)"
description: "ES400A_TunSelnMngt_Impl: EPS system service `TunSelnMngt` (ES400A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Tuning Selection Management (ES400A)

Repo directory: `ES400A_TunSelnMngt_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `TunSelnMngt` (ES400A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES400A_TunSelnMngt_Impl/src/TunSelnMngt.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `TunSelnMngt.c`, `TunSelnMngt_private.c`
- `include/` (1 entries): `TunSelnMngt.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `TunSelnMngt.dcf`, `TunSelnMngt_attr_def.xml`, `TunSelnMngt_bswmd.arxml`
- `generate/` (3 entries): `TunSelnMngt_Cfg_private.c.tt`, `TunSelnMngt_Cfg_private.h.tt`, `TunSelnMngt_Generate.bat`
- `tools/` (12 entries): `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `ES400A_TunSelnMngt_Impl.gpj`, `Integrate.bat`, `IntegrationCopy`, `Polyspace`, `QAC`, `RteGen.bat`, `TunSelnMngt.dpa`, `contract`
- `doc/` (5 entries): `ES400A_TunSelnMngt_Integration_Manual.doc`, `ES400A_TunSelnMngt_MDD.docx`, `Polyspace_Results`, `QAC_Results`, `TunSelnMngt_PeerReview.xlsm`

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

- [ES400A_TunSelnMngt_Integration_Manual.doc](./es400a-tunselnmngt-integration-manual/)
- [ES400A_TunSelnMngt_MDD.docx](./es400a-tunselnmngt-mdd/)

## Repository location

Repo path: `ES400A_TunSelnMngt_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `generate/`.
