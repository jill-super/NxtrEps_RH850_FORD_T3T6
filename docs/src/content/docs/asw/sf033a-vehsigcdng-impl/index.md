---
title: "Vehicle Signal Coding (SF033A)"
description: "SF033A_VehSigCdng_Impl: Application SW-C `VehSigCdng` (SF033A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook a"
---


import { Badge } from '@astrojs/starlight/components';

# Vehicle Signal Coding (SF033A)

Repo directory: `SF033A_VehSigCdng_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `VehSigCdng` (SF033A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF033A_VehSigCdng_Impl/src/VehSigCdng.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `VehSigCdng.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `VehSigCdng.dcf`, `VehSigCdng_attr_def.xml`
- `tools/` (5 entries): `Component.dpa`, `Polyspace`, `SF033A_VehSigCdng_Impl.gpj`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `Polyspace`, `VehSigCdng_Integration Manual.doc`, `VehSigCdng_MDD.docx`, `VehSigCdng_PeerReviewChecklist.xlsm`

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

- [VehSigCdng_Integration Manual.doc](./vehsigcdng-integration-manual/)
- [VehSigCdng_MDD.docx](./vehsigcdng-mdd/)

## Repository location

Repo path: `SF033A_VehSigCdng_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
