---
title: "End of Travel Learning (SF011A)"
description: "SF011A_EotLrng_Impl: Application SW-C `EotLrng` (SF011A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and "
---


import { Badge } from '@astrojs/starlight/components';

# End of Travel Learning (SF011A)

Repo directory: `SF011A_EotLrng_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `EotLrng` (SF011A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF011A_EotLrng_Impl/src/EotLrng.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `EotLrng.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `EotLrng.dcf`, `EotLrng_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `Component.dpa`, `Polyspace`, `SF011A_EotLrng_Impl.gpj`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `EotLrng_IntegrationManual.doc`, `EotLrng_MDD.doc`, `EotLrng_Review.xlsm`, `Polyspace`

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

- [EotLrng_IntegrationManual.doc](./eotlrng-integrationmanual/)
- [EotLrng_MDD.doc](./eotlrng-mdd/)

## Repository location

Repo path: `SF011A_EotLrng_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
