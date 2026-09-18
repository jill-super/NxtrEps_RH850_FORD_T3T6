---
title: "Ford Message 4B0 — High-Speed Bus (MM089A)"
description: "MM089A_FordMsg4B0BusHiSpd_Impl: CAN message gateway SW-C for Ford Hi-Speed message `FordMsg4B0BusHiSpd` (MM089A). Maps COM-stack signals to application ports (and back) for that frame."
---


import { Badge } from '@astrojs/starlight/components';

# Ford Message 4B0 — High-Speed Bus (MM089A)

Repo directory: `MM089A_FordMsg4B0BusHiSpd_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

CAN message gateway SW-C for Ford Hi-Speed message `FordMsg4B0BusHiSpd` (MM089A). Maps COM-stack signals to application ports (and back) for that frame.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `MM089A_FordMsg4B0BusHiSpd_Impl/src/FordMsg4B0BusHiSpd.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `FordMsg4B0BusHiSpd.c`, `FordMsg4B0BusHiSpdNonRte.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `FordMsg4B0BusHiSpd.dcf`, `FordMsg4B0BusHiSpd_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `Component.dpa`, `MM089A_FordMsg4B0BusHiSpd_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `FordMsg4B0BusHiSpd_IntegrationManual.doc`, `FordMsg4B0BusHiSpd_MDD.docx`, `FordMsg4B0BusHiSpd_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [FordMsg4B0BusHiSpd_IntegrationManual.doc](./fordmsg4b0bushispd-integrationmanual/)
- [FordMsg4B0BusHiSpd_MDD.docx](./fordmsg4b0bushispd-mdd/)

## Repository location

Repo path: `MM089A_FordMsg4B0BusHiSpd_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
