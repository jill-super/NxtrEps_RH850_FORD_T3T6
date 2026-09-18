---
title: "Damping (SF003A)"
description: "SF003A_Dampg_Impl: Application SW-C `Dampg` (SF003A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and ve"
---


import { Badge } from '@astrojs/starlight/components';

# Damping (SF003A)

Repo directory: `SF003A_Dampg_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `Dampg` (SF003A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF003A_Dampg_Impl/src/Dampg.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `Dampg.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `Dampg.dcf`, `Dampg_attr_def.xml`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (6 entries): `Component.dpa`, `Polyspace`, `RteGen.bat`, `SF003A_Dampg_Impl.gpj`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `Dampg_IntegrationManual.doc`, `Dampg_MDD.docx`, `Dampg_Peer_Review_Checklist.xlsm`, `Polyspace`

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

- [Dampg_IntegrationManual.doc](./dampg-integrationmanual/)
- [Dampg_MDD.docx](./dampg-mdd/)

## Repository location

Repo path: `SF003A_Dampg_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
