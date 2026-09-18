---
title: "Motor Current Regulator Voltage Limiter (SF105A)"
description: "SF105A_MotCurrRegVltgLimr_Impl: Application SW-C `MotCurrRegVltgLimr` (SF105A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` da"
---


import { Badge } from '@astrojs/starlight/components';

# Motor Current Regulator Voltage Limiter (SF105A)

Repo directory: `SF105A_MotCurrRegVltgLimr_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `MotCurrRegVltgLimr` (SF105A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF105A_MotCurrRegVltgLimr_Impl/src/CDD_MotCurrRegVltgLimr.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_MotCurrRegVltgLimr.c`, `CDD_MotCurrRegVltgLimr_MotCtrl.c`
- `include/` (2 entries): `CDD_MotCurrRegVltgLimr.h`, `CDD_MotCurrRegVltgLimr_MotCtrl_MemMap.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `MotCurrRegVltgLimr.dcf`, `MotCurrRegVltgLimr_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `Component.dpa`, `Polyspace`, `SF105A_MotCurrRegVltgLimr_Impl.gpj`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `MotCurrRegVltgLimr_Integration Manual.docx`, `MotCurrRegVltgLimr_MDD.docx`, `MotCurrRegVltgLimr_Peer Review Checklists.xlsm`, `Polyspace`

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

- [MotCurrRegVltgLimr_Integration Manual.docx](./motcurrregvltglimr-integration-manual/)
- [MotCurrRegVltgLimr_MDD.docx](./motcurrregvltglimr-mdd/)

## Repository location

Repo path: `SF105A_MotCurrRegVltgLimr_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
