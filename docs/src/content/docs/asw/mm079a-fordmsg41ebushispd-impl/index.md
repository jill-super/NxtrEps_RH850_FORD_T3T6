---
title: "Ford Message 41E — High-Speed Bus (MM079A)"
description: "MM079A_FordMsg41EBusHiSpd_Impl: CAN message gateway SW-C for Ford Hi-Speed message `FordMsg41EBusHiSpd` (MM079A). Maps COM-stack signals to application ports (and back) for that frame."
---


import { Badge } from '@astrojs/starlight/components';

# Ford Message 41E — High-Speed Bus (MM079A)

Repo directory: `MM079A_FordMsg41EBusHiSpd_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

CAN message gateway SW-C for Ford Hi-Speed message `FordMsg41EBusHiSpd` (MM079A). Maps COM-stack signals to application ports (and back) for that frame.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `MM079A_FordMsg41EBusHiSpd_Impl/src/FordMsg41EBusHiSpd.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `FordMsg41EBusHiSpd.c`, `FordMsg41EBusHiSpdNonRte.c`
- `autosar/` (13 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `Constants.arxml`, `Constants_gen_attr.xml`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `FordMsg41EBusHiSpd.dcf`, `FordMsg41EBusHiSpd_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `Component.dpa`, `MM079A_FordMsg41EBusHiSpd_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `FordMsg41EBusHiSpd_IntegrationManual.doc`, `FordMsg41EBusHiSpd_MDD.doc`, `FordMsg41EBusHiSpd_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [FordMsg41EBusHiSpd_IntegrationManual.doc](./fordmsg41ebushispd-integrationmanual/)
- [FordMsg41EBusHiSpd_MDD.doc](./fordmsg41ebushispd-mdd/)

## Repository location

Repo path: `MM079A_FordMsg41EBusHiSpd_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
