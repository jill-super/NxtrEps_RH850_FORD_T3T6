---
title: "ECM Output and Diagnostics (CM104B)"
description: "CM104B_EcmOutpAndDiagc_Impl: Complex driver `EcmOutpAndDiagc` (CM104B): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# ECM Output and Diagnostics (CM104B)

Repo directory: `CM104B_EcmOutpAndDiagc_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `EcmOutpAndDiagc` (CM104B): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM104B_EcmOutpAndDiagc_Impl/src/CDD_EcmOutpAndDiagc.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_EcmOutpAndDiagc.c`, `CDD_EcmOutpAndDiagcNonRte.c`
- `include/` (1 entries): `CDD_EcmOutpAndDiagc.h`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `EcmOutpAndDiagc.dcf`, `EcmOutpAndDiagc_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `CM104B_EcmOutpAndDiagc_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `EcmOutpAndDiagc_IntegrationManual.doc`, `EcmOutpAndDiagc_MDD.docx`, `EcmOutpAndDiagc_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [EcmOutpAndDiagc_IntegrationManual.doc](./ecmoutpanddiagc-integrationmanual/)
- [EcmOutpAndDiagc_MDD.docx](./ecmoutpanddiagc-mdd/)

## Repository location

Repo path: `CM104B_EcmOutpAndDiagc_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
