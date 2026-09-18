---
title: "Diagnostics Manager (ES101A)"
description: "ES101A_DiagcMgr_Impl: EPS system service `DiagcMgr` (ES101A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function."
---


import { Badge } from '@astrojs/starlight/components';

# Diagnostics Manager (ES101A)

Repo directory: `ES101A_DiagcMgr_Impl/` · Layer: `cdd`

<Badge text="Custom · Nexteer in-house" variant="success" />

## Purpose and responsibility

EPS system service `DiagcMgr` (ES101A): sensing, power, thermal, NvM, diagnostic or motor-control support around the steering function.

## Origin

**Custom · Nexteer in-house.** Nexteer copyright header in `ES101A_DiagcMgr_Impl/src/DiagcMgr.c` (in-house; RTE/generator headers may still mention Vector).

:::note[In-house code]
Project-owned sources. RTE/generator headers inside `tools/` may still mention Vector — that identifies the *generator*, not the owner. :::

## Key files

- `src/` (15 entries): `DiagcMgr.c`, `DiagcMgrNonRTE.c`, `DiagcMgrProxyAppl0.c`, `DiagcMgrProxyAppl1.c`, `DiagcMgrProxyAppl10.c`, `DiagcMgrProxyAppl2.c`, `DiagcMgrProxyAppl3.c`, `DiagcMgrProxyAppl4.c`, `DiagcMgrProxyAppl5.c`, `DiagcMgrProxyAppl6.c`, `DiagcMgrProxyAppl7.c`, `DiagcMgrProxyAppl8.c`, `DiagcMgrProxyAppl9.c`, `DiagcMgrStub.c` (+1 more)
- `include/` (3 entries): `DiagcMgr.h`, `DiagcMgrStaticTypes.h`, `DiagcMgr_private.h`
- `autosar/` (12 entries): `AUTOSAR_4-0-3.xsd`, `ComponentTypes`, `DataTypes.arxml`, `DataTypes_gen_attr.xml`, `DiagcMgr.dcf`, `DiagcMgr_attr_def.xml`, `DiagcMgr_bswmd.arxml`, `Packages.arxml`, `Packages_gen_attr.xml`, `PortInterfaces.arxml`, `PortInterfaces_gen_attr.xml`, `ProfileSettings.xml`
- `tools/` (19 entries): `Component.dpa`, `ES101A_DiagcMgr_Impl.gpj`, `ES101A_DiagcMgr_Impl_Appl0.gpj`, `ES101A_DiagcMgr_Impl_Appl1.gpj`, `ES101A_DiagcMgr_Impl_Appl10.gpj`, `ES101A_DiagcMgr_Impl_Appl2.gpj`, `ES101A_DiagcMgr_Impl_Appl3.gpj`, `ES101A_DiagcMgr_Impl_Appl4.gpj`, `ES101A_DiagcMgr_Impl_Appl5.gpj`, `ES101A_DiagcMgr_Impl_Appl6.gpj`, `ES101A_DiagcMgr_Impl_Appl7.gpj`, `ES101A_DiagcMgr_Impl_Appl8.gpj`, `ES101A_DiagcMgr_Impl_Appl9.gpj`, `ES101A_DiagcMgr_Impl_Stub.gpj` (+5 more)
- `doc/` (5 entries): `DiagcMgrProxy_MDD.doc`, `DiagcMgr_IntegrationManual.doc`, `DiagcMgr_MDD.doc`, `DiagcMgr_PeerReviewChecklist.xlsm`, `Polyspace`

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

- [DiagcMgrProxy_MDD.doc](./diagcmgrproxy-mdd/)
- [DiagcMgr_IntegrationManual.doc](./diagcmgr-integrationmanual/)
- [DiagcMgr_MDD.doc](./diagcmgr-mdd/)

## Repository location

Repo path: `ES101A_DiagcMgr_Impl/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`.
