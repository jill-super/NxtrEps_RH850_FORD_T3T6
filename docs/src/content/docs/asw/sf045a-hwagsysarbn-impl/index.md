---
title: "Handwheel Angle System Arbitration (SF045A)"
description: "SF045A_HwAgSysArbn_Impl: Application SW-C `HwAgSysArbn` (SF045A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook "
---


import { Badge } from '@astrojs/starlight/components';

# Handwheel Angle System Arbitration (SF045A)

Repo directory: `SF045A_HwAgSysArbn_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `HwAgSysArbn` (SF045A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF045A_HwAgSysArbn_Impl/src/HwAgSysArbn.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `HwAgSysArbn.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `HwAgSysArbn.dcf`, `HwAgSysArbn_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `Component.dpa`, `Polyspace`, `SF045A_HwAgSysArbn_Impl.gpj`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `HwAgSysArbn_DesignReview.xlsm`, `HwAgSysArbn_Integration Manual.doc`, `HwAgSysArbn_MDD.docx`, `Polyspace`

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

- [HwAgSysArbn_Integration Manual.doc](./hwagsysarbn-integration-manual/)
- [HwAgSysArbn_MDD.docx](./hwagsysarbn-mdd/)

## Repository location

Repo path: `SF045A_HwAgSysArbn_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
