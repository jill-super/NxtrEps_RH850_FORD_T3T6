---
title: "Damping Path Sum (SF035B)"
description: "SF035B_DampgPahSum_Impl: Application SW-C `DampgPahSum` (SF035B steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook "
---


import { Badge } from '@astrojs/starlight/components';

# Damping Path Sum (SF035B)

Repo directory: `SF035B_DampgPahSum_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `DampgPahSum` (SF035B steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF035B_DampgPahSum_Impl/src/DampgPahSum.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `DampgPahSum.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DampgPahSum.dcf`, `DampgPahSum_attr_def.xml`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (6 entries): `Component.dpa`, `Component.nz3541.silent.dcusr`, `Polyspace`, `SF035B_DampgPahSum_Impl.gpj`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `DampgPahSum_IntegrationManual.doc`, `DampgPahSum_MDD.doc`, `DampgPahSum_Peer_Review_Checklist.xlsm`, `Polyspace`

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

- [DampgPahSum_IntegrationManual.doc](./dampgpahsum-integrationmanual/)
- [DampgPahSum_MDD.doc](./dampgpahsum-mdd/)

## Repository location

Repo path: `SF035B_DampgPahSum_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
