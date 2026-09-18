---
title: "Ford Message 5B5 — High-Speed Bus (MM519A)"
description: "MM519A_FordMsg5B5BusHiSpd_Impl: CAN message gateway SW-C for Ford Hi-Speed message `FordMsg5B5BusHiSpd` (MM519A). Maps COM-stack signals to application ports (and back) for that frame."
---


import { Badge } from '@astrojs/starlight/components';

# Ford Message 5B5 — High-Speed Bus (MM519A)

Repo directory: `MM519A_FordMsg5B5BusHiSpd_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

CAN message gateway SW-C for Ford Hi-Speed message `FordMsg5B5BusHiSpd` (MM519A). Maps COM-stack signals to application ports (and back) for that frame.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `MM519A_FordMsg5B5BusHiSpd_Impl/src/FordMsg5B5BusHiSpd.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `FordMsg5B5BusHiSpd.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `FordMsg5B5BusHiSpd.dcf`, `FordMsg5B5BusHiSpd_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `Component.dpa`, `MM519A_FordMsg5B5BusHiSpd_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `FordMsg5B5BusHiSpd_IntegrationManual.doc`, `FordMsg5B5BusHiSpd_MDD.doc`, `FordMsg5B5BusHiSpd_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [FordMsg5B5BusHiSpd_IntegrationManual.doc](./fordmsg5b5bushispd-integrationmanual/)
- [FordMsg5B5BusHiSpd_MDD.doc](./fordmsg5b5bushispd-mdd/)

## Repository location

Repo path: `MM519A_FordMsg5B5BusHiSpd_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
