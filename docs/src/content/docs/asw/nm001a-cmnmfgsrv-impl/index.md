---
title: "Common Manufacturing Service (NM001A)"
description: "NM001A_CmnMfgSrv_Impl: Manufacturing/service SW-C `CmnMfgSrv` (NM001A): software/part IDs, motor-velocity control support or common MFG services."
---


import { Badge } from '@astrojs/starlight/components';

# Common Manufacturing Service (NM001A)

Repo directory: `NM001A_CmnMfgSrv_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Manufacturing/service SW-C `CmnMfgSrv` (NM001A): software/part IDs, motor-velocity control support or common MFG services.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `NM001A_CmnMfgSrv_Impl/src/CmnMfgSrv.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (186 entries): `CmnMfgSrv.c`, `CmnMfgSrvFct.c`, `SrvF000.c`, `SrvF001.c`, `SrvF002.c`, `SrvF010.c`, `SrvF100.c`, `SrvF101.c`, `SrvF110.c`, `SrvF111.c`, `SrvF112.c`, `SrvF113.c`, `SrvF114.c`, `SrvF115.c` (+172 more)
- `include/` (3 entries): `CmnMfgSrv.h`, `CmnMfgSrvFct.h`, `CmnMfgSrvTyp.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `CmnMfgSrv.dcf`, `CmnMfgSrv_attr_def.xml`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `NxtrMfgSrv_bswmd.arxml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `generate/` (3 entries): `MfgSrvCfg.c.tt`, `MfgSrvCfg.h.tt`, `NxtrMfgSrv_Generate.bat`
- `tools/` (15 entries): `CmnMfgSrv.dpa`, `CmnMfgSrvCfg.arxml`, `Component.ecuc.arxml`, `Component_Rte_ecuc.arxml`, `Config`, `CreateGHSProject.bat`, `CreatePolyspaceProject.bat`, `CreateQACProject.bat`, `Integrate.bat`, `IntegrationCopy`, `NM001A_CmnMfgSrv_Impl.gpj`, `OdxGen.bat`, `QAC`, `RteGen.bat` (+1 more)
- `doc/` (6 entries): `CmnMfgSrv.odx-d`, `CmnMfgSrv_PeerReviewChecklist.xlsm`, `NM001A_CmnMfgSrv_DataDict.m`, `QAC_Results`, `guides`, `reference`

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

- [Development.txt](./development/)
- [Integration.txt](./integration/)
- [OdxGuide.txt](./odxguide/)
- [README.txt](./readme/)

## Repository location

Repo path: `NM001A_CmnMfgSrv_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `generate/`.
