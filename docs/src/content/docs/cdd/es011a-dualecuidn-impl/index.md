---
title: "Dual ECU Identification (ES011A)"
description: "ES011A_DualEcuIdn_Impl: EPS system service `DualEcuIdn` (ES011A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Dual ECU Identification (ES011A)

Repo directory: `ES011A_DualEcuIdn_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `DualEcuIdn` (ES011A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES011A_DualEcuIdn_Impl/src/DualEcuIdn.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `DualEcuIdn.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `DualEcuIdn.dcf`, `DualEcuIdn_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (6 entries): `Component.dpa`, `Component.nz3541.silent.dcusr`, `ES011A_DualEcuIdn_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `DualEcuIdn_IntegrationManual.docx`, `DualEcuIdn_MDD.doc`, `DualEcuIdn_ReviewChecklist.xlsm`, `Polyspace`

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

- [DualEcuIdn_IntegrationManual.docx](./dualecuidn-integrationmanual/)
- [DualEcuIdn_MDD.doc](./dualecuidn-mdd/)

## Repository location

Repo path: `ES011A_DualEcuIdn_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
