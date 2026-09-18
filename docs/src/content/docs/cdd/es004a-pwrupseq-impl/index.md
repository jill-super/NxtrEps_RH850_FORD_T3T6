---
title: "Power Up Sequence (ES004A)"
description: "ES004A_PwrUpSeq_Impl: EPS system service `PwrUpSeq` (ES004A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Power Up Sequence (ES004A)

Repo directory: `ES004A_PwrUpSeq_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `PwrUpSeq` (ES004A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES004A_PwrUpSeq_Impl/src/PwrUpSeq.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `PwrUpSeq.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `PwrUpSeq.dcf`, `PwrUpSeq_attr_def.xml`
- `tools/` (6 entries): `Component.dpa`, `Component.nz3541.silent.dcusr`, `ES004A_PwrUpSeq_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (5 entries): `Polyspace`, `Polyspace_Results`, `PwrUpSeq_IntegrationManual.doc`, `PwrUpSeq_MDD.doc`, `PwrUpSeq_PeerReviewChecklist.xlsm`

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

- [PwrUpSeq_IntegrationManual.doc](./pwrupseq-integrationmanual/)
- [PwrUpSeq_MDD.doc](./pwrupseq-mdd/)

## Repository location

Repo path: `ES004A_PwrUpSeq_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
