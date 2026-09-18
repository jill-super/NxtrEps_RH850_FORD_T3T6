---
title: "System Friction Learning (SF007A)"
description: "SF007A_SysFricLrng_Impl: Application SW-C `SysFricLrng` (SF007A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook "
---


import { Badge } from '@astrojs/starlight/components';

# System Friction Learning (SF007A)

Repo directory: `SF007A_SysFricLrng_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `SysFricLrng` (SF007A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF007A_SysFricLrng_Impl/src/SysFricLrng.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `SysFricLrng.c`, `SysFricLrngNonRte.c`
- `include/` (1 entries): `SysFricLrng.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `SysFricLrng.dcf`, `SysFricLrng_attr_def.xml`
- `tools/` (5 entries): `Component.dpa`, `Polyspace`, `SF007A_SysFricLrng_Impl.gpj`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `Polyspace`, `SysFricLrng_IntegrationManual.doc`, `SysFricLrng_MDD.docx`, `SysFricLrng_PeerReviewChecklists.xlsm`

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

- [SysFricLrng_IntegrationManual.doc](./sysfriclrng-integrationmanual/)
- [SysFricLrng_MDD.docx](./sysfriclrng-mdd/)

## Repository location

Repo path: `SF007A_SysFricLrng_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
