---
title: "Assist Path Sum (SF034B)"
description: "SF034B_AssiPahSum_Impl: Application SW-C `AssiPahSum` (SF034B steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook a"
---


import { Badge } from '@astrojs/starlight/components';

# Assist Path Sum (SF034B)

Repo directory: `SF034B_AssiPahSum_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `AssiPahSum` (SF034B steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF034B_AssiPahSum_Impl/src/AssiPahSum.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `AssiPahSum.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `AssiPahSum.dcf`, `AssiPahSum_attr_def.xml`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `Component.dpa`, `Polyspace`, `SF034B_AssiPahSum_Impl.gpj`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `AssiPahSum_IntegrationManual.doc`, `AssiPahSum_MDD.doc`, `AssiPahSum_Peer_Review_Checklist.xlsm`, `Polyspace`

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

- [AssiPahSum_IntegrationManual.doc](./assipahsum-integrationmanual/)
- [AssiPahSum_MDD.doc](./assipahsum-mdd/)

## Repository location

Repo path: `SF034B_AssiPahSum_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
