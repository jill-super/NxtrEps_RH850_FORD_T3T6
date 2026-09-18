---
title: "Sync CRC (CM800A)"
description: "CM800A_SyncCrc_Impl: Complex driver `SyncCrc` (CM800A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# Sync CRC (CM800A)

Repo directory: `CM800A_SyncCrc_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `SyncCrc` (CM800A): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM800A_SyncCrc_Impl/src/CDD_SyncCrc.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_SyncCrc.c`, `CDD_SyncCrcNonRte.c`
- `include/` (2 entries): `CDD_SyncCrc.h`, `CDD_SyncCrc_private.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `SyncCrc.dcf`, `SyncCrc_attr_def.xml`, `SyncCrc_bswmd.arxml`
- `tools/` (7 entries): `CM800A_SyncCrc_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`, `template`
- `doc/` (4 entries): `CM800A_SycnCrc_MDD.docx`, `CM800A_SyncCrc_Integration_Manual.doc`, `Polyspace`, `SyncCrc Review.xlsm`

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

- [CM800A_SycnCrc_MDD.docx](./cm800a-sycncrc-mdd/)
- [CM800A_SyncCrc_Integration_Manual.doc](./cm800a-synccrc-integration-manual/)

## Repository location

Repo path: `CM800A_SyncCrc_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
