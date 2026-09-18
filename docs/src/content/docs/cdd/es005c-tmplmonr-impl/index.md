---
title: "Tmpl monitor (ES005C)"
description: "ES005C_TmplMonr_Impl: EPS system service `TmplMonr` (ES005C): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Tmpl monitor (ES005C)

Repo directory: `ES005C_TmplMonr_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `TmplMonr` (ES005C): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES005C_TmplMonr_Impl/src/TmplMonr.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (1 entries): `TmplMonr.c`
- `autosar/` (11 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`, `TmplMonr.dcf`, `TmplMonr_attr_def.xml`
- `tools/` (5 entries): `Component.dpa`, `ES005C_TmplMonr_Impl.gpj`, `Polyspace`, `SWCSupport.bat`, `local`
- `doc/` (4 entries): `Polyspace`, `TmplMonr_IntegrationManual.doc`, `TmplMonr_MDD.doc`, `TmplMonr_PeerReviewChecklist.xlsm`

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

- [TmplMonr_IntegrationManual.doc](./tmplmonr-integrationmanual/)
- [TmplMonr_MDD.doc](./tmplmonr-mdd/)

## Repository location

Repo path: `ES005C_TmplMonr_Impl/` — subfolders present: `src/`, `autosar/`, `doc/`, `tools/`.
