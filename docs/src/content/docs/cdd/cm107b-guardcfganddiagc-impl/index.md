---
title: "Guard Configuration and Diagnostics (CM107B)"
description: "CM107B_GuardCfgAndDiagc_Impl: Complex driver `GuardCfgAndDiagc` (CM107B): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access."
---


import { Badge } from '@astrojs/starlight/components';

# Guard Configuration and Diagnostics (CM107B)

Repo directory: `CM107B_GuardCfgAndDiagc_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Complex driver `GuardCfgAndDiagc` (CM107B): MCU/peripheral configuration, measurement front-end or diagnostics with direct hardware access.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `CM107B_GuardCfgAndDiagc_Impl/src/CDD_GuardCfgAndDiagc.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_GuardCfgAndDiagc.c`, `CDD_GuardCfgAndDiagcNonRte.c`
- `include/` (1 entries): `CDD_GuardCfgAndDiagc.h`
- `autosar/` (7 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `GuardCfgAndDiagc.dcf`, `GuardCfgAndDiagc_attr_def.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (5 entries): `CM107B_GuardCfgAndDiagc_Impl.gpj`, `Component.dpa`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `GuardCfgAndDiagc Integration Manual.doc`, `GuardCfgAndDiagc Module Design Document.docx`, `GuardCfgAndDiagc_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [GuardCfgAndDiagc Integration Manual.doc](./guardcfganddiagc-integration-manual/)
- [GuardCfgAndDiagc Module Design Document.docx](./guardcfganddiagc-module-design-document/)

## Repository location

Repo path: `CM107B_GuardCfgAndDiagc_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
