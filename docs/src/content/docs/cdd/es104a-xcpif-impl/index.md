---
title: "XCP Interface (ES104A)"
description: "ES104A_XcpIf_Impl: EPS system service `XcpIf` (ES104A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# XCP Interface (ES104A)

Repo directory: `ES104A_XcpIf_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `XcpIf` (ES104A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES104A_XcpIf_Impl/src/CDD_XcpIf.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `CDD_XcpIf.c`
- `include/` (2 entries): `CDD_XcpIf.h`, `CDD_XcpIf_private.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `CDD_XcpIf.dcf`, `CDD_XcpIf_attr_def.xml`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `XcpIf_bswmd.arxml`
- `generate/` (2 entries): `CDD_XcpIf_Cfg.h.tt`, `XcpIf_Generate.bat`
- `tools/` (15 entries): `CDD_XcpIf.dpa`, `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `ES104A_XcpIf_Impl.gpj`, `Integrate.bat`, `IntegrationCopy`, `Polyspace`, `QAC`, `RteGen.bat`, `XcpIf.dpa` (+1 more)
- `doc/` (5 entries): `Polyspace_Results`, `QAC_Results`, `XcpIf Integration Manual.docx`, `XcpIf Peer Review Checklists.xlsm`, `XcpIf_MDD.docx`

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

- [XcpIf Integration Manual.docx](./xcpif-integration-manual/)
- [XcpIf_MDD.docx](./xcpif-mdd/)

## Repository location

Repo path: `ES104A_XcpIf_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `generate/`.
