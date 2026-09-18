---
title: "Inter-Micro Communication Arbitration (AR350A)"
description: "AR350A_ImcArbn_Impl: Inter-micro communication arbiter shared by dual-controller paths."
---


import { Badge } from '@astrojs/starlight/components';

# Inter-Micro Communication Arbitration (AR350A)

Repo directory: `AR350A_ImcArbn_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Inter-micro communication arbiter shared by dual-controller paths.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `AR350A_ImcArbn_Impl/src/ImcArbn.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `ImcArbn.c`
- `include/` (1 entries): `ImcArbn.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `ImcArbn.dcf`, `ImcArbn_attr_def.xml`, `ImcArbn_bswmd.arxml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (7 entries): `AR350A_ImcArbn_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`, `template`
- `doc/` (4 entries): `ImcArbn_IntegrationManual.doc`, `ImcArbn_MDD.doc`, `ImcArbn_Review.xlsm`, `Polyspace`

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

- [ImcArbn_IntegrationManual.doc](./imcarbn-integrationmanual/)
- [ImcArbn_MDD.doc](./imcarbn-mdd/)

## Repository location

Repo path: `AR350A_ImcArbn_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
