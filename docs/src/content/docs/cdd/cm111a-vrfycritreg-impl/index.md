---
title: "Critical register verification (CM111A)"
description: "CM111A_VrfyCritReg_Impl: Complex driver `VrfyCritReg` (CM111A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# Critical register verification (CM111A)

Repo directory: `CM111A_VrfyCritReg_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `VrfyCritReg` (CM111A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM111A_VrfyCritReg_Impl/src/CDD_VrfyCritReg.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `CDD_VrfyCritReg.c`
- `include/` (1 entries): `CDD_VrfyCritReg.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `CDD_VrfyCritReg_bswmd.arxml`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `VrfyCritReg.dcf`, `VrfyCritReg_attr_def.xml`
- `generate/` (4 entries): `CDD_VrfyCritReg_Cfg.c.tt`, `CDD_VrfyCritReg_Cfg_private.h.tt`, `CDD_VrfyCritReg_Generate.bat`, `CDD_VrfyCritReg_helper.tt`
- `tools/` (7 entries): `CM111A_VrfyCritReg_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`, `template`
- `doc/` (4 entries): `Polyspace`, `VrfyCritReg_IntegrationManual.doc`, `VrfyCritReg_MDD.docx`, `VrfyCritReg_Review.xlsm`

## Generated code and configuration

- Local generation output: `tools/local/generate/`.
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

- [VrfyCritReg_IntegrationManual.doc](./vrfycritreg-integrationmanual/)
- [VrfyCritReg_MDD.docx](./vrfycritreg-mdd/)

## Repository location

Repo path: `CM111A_VrfyCritReg_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `generate/`.
