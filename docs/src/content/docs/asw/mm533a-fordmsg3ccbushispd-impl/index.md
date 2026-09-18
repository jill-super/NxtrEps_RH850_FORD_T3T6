---
title: "Ford Message 3CC — High-Speed Bus (MM533A)"
description: "MM533A_FordMsg3CCBusHiSpd_Impl: CAN message gateway SW-C for Ford Hi-Speed message `FordMsg3CCBusHiSpd` (MM533A). Maps COM-stack signals to application ports (and back) for that frame."
---


import { Badge } from '@astrojs/starlight/components';

# Ford Message 3CC — High-Speed Bus (MM533A)

Repo directory: `MM533A_FordMsg3CCBusHiSpd_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

CAN message gateway SW-C for Ford Hi-Speed message `FordMsg3CCBusHiSpd` (MM533A). Maps COM-stack signals to application ports (and back) for that frame.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `MM533A_FordMsg3CCBusHiSpd_Impl/src/FordMsg3CCBusHiSpd.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `FordMsg3CCBusHiSpd.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `FordMsg3CCBusHiSpd.dcf`, `FordMsg3CCBusHiSpd_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `Component.dpa`, `MM533A_FordMsg3CCBusHiSpd_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `FordMsg3CCBusHiSpd_IntegrationManual.doc`, `FordMsg3CCBusHiSpd_PeerReviewChecklist.xlsm`, `MM533A_FordMsg3CCBusHiSpd_MDD.docx`, `Polyspace`

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

- [FordMsg3CCBusHiSpd_IntegrationManual.doc](./fordmsg3ccbushispd-integrationmanual/)
- [MM533A_FordMsg3CCBusHiSpd_MDD.docx](./mm533a-fordmsg3ccbushispd-mdd/)

## Repository location

Repo path: `MM533A_FordMsg3CCBusHiSpd_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
