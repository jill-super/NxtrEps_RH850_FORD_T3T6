---
title: "Ford Handwheel Torque Coding (CF076A)"
description: "CF076A_FordHwTqCdng_Impl: Ford customer-feature SW-C `FordHwTqCdng` (CF076A). Implements Ford-specific arbitration, coding or black-box-interface logic on top of platform signals."
---


import { Badge } from '@astrojs/starlight/components';

# Ford Handwheel Torque Coding (CF076A)

Repo directory: `CF076A_FordHwTqCdng_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Ford customer-feature SW-C `FordHwTqCdng` (CF076A). Implements Ford-specific arbitration, coding or black-box-interface logic on top of platform signals.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CF076A_FordHwTqCdng_Impl/src/FordHwTqCdng.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `FordHwTqCdng.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `FordHwTqCdng.dcf`, `FordHwTqCdng_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `CF076A_FordHwTqCdng_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `FordHwTqCdng_IntegrationManual.doc`, `FordHwTqCdng_MDD.doc`, `FordHwTqCdng_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [FordHwTqCdng_IntegrationManual.doc](./fordhwtqcdng-integrationmanual/)
- [FordHwTqCdng_MDD.doc](./fordhwtqcdng-mdd/)

## Repository location

Repo path: `CF076A_FordHwTqCdng_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
