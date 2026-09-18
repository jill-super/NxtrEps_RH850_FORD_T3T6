---
title: "Ford Message 415 — High-Speed Bus (MM077A)"
description: "MM077A_FordMsg415BusHiSpd_Impl: CAN message gateway SW-C for Ford Hi-Speed message `FordMsg415BusHiSpd` (MM077A). Maps COM-stack signals to application ports (and back) for that frame."
---


import { Badge } from '@astrojs/starlight/components';

# Ford Message 415 — High-Speed Bus (MM077A)

Repo directory: `MM077A_FordMsg415BusHiSpd_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

CAN message gateway SW-C for Ford Hi-Speed message `FordMsg415BusHiSpd` (MM077A). Maps COM-stack signals to application ports (and back) for that frame.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `MM077A_FordMsg415BusHiSpd_Impl/src/FordMsg415BusHiSpd.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `FordMsg415BusHiSpd.c`, `FordMsg415BusHiSpdNonRte.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `FordMsg415BusHiSpd.dcf`, `FordMsg415BusHiSpd_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `Component.dpa`, `MM077A_FordMsg415BusHiSpd_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `FordMsg415BusHiSpd_IntegrationManual.doc`, `FordMsg415BusHiSpd_MDD.doc`, `FordMsg415BusHiSpd_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [FordMsg415BusHiSpd_IntegrationManual.doc](./fordmsg415bushispd-integrationmanual/)
- [FordMsg415BusHiSpd_MDD.doc](./fordmsg415bushispd-mdd/)

## Repository location

Repo path: `MM077A_FordMsg415BusHiSpd_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
