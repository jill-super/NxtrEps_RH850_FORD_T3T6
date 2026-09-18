---
title: "Tuning Selection Authority (SF023A)"
description: "SF023A_TunSelnAuthy_Impl: Application SW-C `TunSelnAuthy` (SF023A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook"
---


import { Badge } from '@astrojs/starlight/components';

# Tuning Selection Authority (SF023A)

Repo directory: `SF023A_TunSelnAuthy_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `TunSelnAuthy` (SF023A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF023A_TunSelnAuthy_Impl/src/TunSelnAuthy.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `TunSelnAuthy.c`
- `include/` (1 entries): `TunSelnAuthy.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `TunSelnAuthy.dcf`, `TunSelnAuthy_attr_def.xml`
- `tools/` (6 entries): `Component.dpa`, `Component.nz3734.silent.dcusr`, `Polyspace`, `SF023A_TunSelnAuthy_Impl.gpj`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `Polyspace`, `TunSelnAuthy_IntegrationManual.doc`, `TunSelnAuthy_MDD.docx`, `TunSelnAuthy_PeerReview.xlsm`

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

- [TunSelnAuthy_IntegrationManual.doc](./tunselnauthy-integrationmanual/)
- [TunSelnAuthy_MDD.docx](./tunselnauthy-mdd/)

## Repository location

Repo path: `SF023A_TunSelnAuthy_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
