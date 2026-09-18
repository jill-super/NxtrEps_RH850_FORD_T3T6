---
title: "Return (SF002A)"
description: "SF002A_Rtn_Impl: Application SW-C `Rtn` (SF002A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and veri"
---


import { Badge } from '@astrojs/starlight/components';

# Return (SF002A)

Repo directory: `SF002A_Rtn_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Application SW-C `Rtn` (SF002A steering-feature cluster). Implements its FDD/MDD control or arbitration function as RTE runnable(s); tunable via the DataDict `.m` databook and verified with the module MDD/integration manual.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `SF002A_Rtn_Impl/src/Rtn.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `Rtn.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `Rtn.dcf`, `Rtn_attr_def.xml`
- `tools/` (6 entries): `Component.NZ3734.silent.dcusr`, `Component.dpa`, `Polyspace`, `SF002A_Rtn_Impl.gpj`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `Polyspace`, `Rtn_Integration Manual.doc`, `Rtn_Module Design Document.docx`, `Rtn_PeerReview.xlsm`

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

- [Rtn_Integration Manual.doc](./rtn-integration-manual/)
- [Rtn_Module Design Document.docx](./rtn-module-design-document/)

## Repository location

Repo path: `SF002A_Rtn_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
