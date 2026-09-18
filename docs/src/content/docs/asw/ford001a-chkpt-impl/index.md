---
title: "Checkpoint monitor (Ford001A)"
description: "Ford001A_ChkPt_Impl: Checkpoint (program-flow monitoring) support component used by safety mechanisms."
---


import { Badge } from '@astrojs/starlight/components';

# Checkpoint monitor (Ford001A)

Repo directory: `Ford001A_ChkPt_Impl/` · Layer: `asw`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

Checkpoint (program-flow monitoring) support component used by safety mechanisms.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `Ford001A_ChkPt_Impl/src/CDD_ChkPtAppl10.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (2 entries): `CDD_ChkPtAppl10.c`, `CDD_ChkPt_Bsw.c`
- `include/` (1 entries): `CDD_ChkPt_Bsw.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ChkPt.dcf`, `ChkPt_attr_def.xml`, `ChkPt_bswmd.arxml`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (7 entries): `Component.dpa`, `Component.gz324f.silent.dcusr`, `Ford001A_ChkPt_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `integrate`, `local`
- `doc/` (2 entries): `ChkPt_PeerReviewChecklist.xlsm`, `Polyspace`

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

- No `.doc`/`.docx`/`.pdf` (or `doc/`-level `.txt`) sources found in this module.

## Repository location

Repo path: `Ford001A_ChkPt_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
