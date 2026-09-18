---
title: "Exception Handling (CM101B)"
description: "CM101B_ExcpnHndlg_Impl: Complex driver `ExcpnHndlg` (CM101B): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# Exception Handling (CM101B)

Repo directory: `CM101B_ExcpnHndlg_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `ExcpnHndlg` (CM101B): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM101B_ExcpnHndlg_Impl/src/CDD_ExcpnHndlg.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (3 entries): `CDD_ExcpnHndlg.c`, `CDD_ExcpnHndlgIrq.c`, `CDD_ExcpnHndlgNonRte.c`
- `include/` (2 entries): `CDD_ExcpnHndlg.h`, `CDD_ExcpnHndlg_private.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `ExcpnHndlg.dcf`, `ExcpnHndlg_attr_def.xml`, `ExcpnHndlg_bswmd.arxml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (8 entries): `CM101B_ExcpnHndlg_Impl.gpj`, `Component.RZK04C.silent.dcusr`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`, `template`
- `doc/` (4 entries): `ExcpnHndlg Integration Manual.doc`, `ExcpnHndlg Module Design Document.docx`, `ExcpnHndlg_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [ExcpnHndlg Integration Manual.doc](./excpnhndlg-integration-manual/)
- [ExcpnHndlg Module Design Document.docx](./excpnhndlg-module-design-document/)

## Repository location

Repo path: `CM101B_ExcpnHndlg_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
