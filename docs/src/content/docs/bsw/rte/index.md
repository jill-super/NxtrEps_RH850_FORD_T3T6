---
title: "Run-Time Environment"
description: "Rte: Run-Time Environment: generated communication layer between SW-Cs and BSW (contracts in each SW-C `tools/contract`, output in the integration `generate/` tree)."
---


import { Badge } from '@astrojs/starlight/components';

# Run-Time Environment

Repo directory: `Rte/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

Run-Time Environment: generated communication layer between SW-Cs and BSW (contracts in each SW-C `tools/contract`, output in the integration `generate/` tree).

## Origin

**Vector-provided · MICROSAR.** Vector MICROSAR RTE generator and analyser; target code is generated into the integration tree.

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `autosar/` (2 entries): `Rte_bswmd.arxml`, `Rte_preo.arxml`
- `generate/` (53 entries): `AllowedTemplateVariants.json`, `DCFServer.dll`, `DTD6.9`, `DTD7.0`, `DTD7.1`, `DTD7.2`, `DTD7.3`, `DTD7.4`, `DTD7.5`, `DTD7.6`, `DTD7.7`, `DVApplicationManifest.dll`, `DVCfgRteGen.exe`, `DVCvt.exe` (+39 more)
- `tools/` (3 entries): `Integrate.bat`, `IntegrationCopy`, `RteAnalyzer`
- `doc/` (5 entries): `AN-ISC-8-1166_RTE_BRE_without_AUTOSAR_OS.pdf`, `ReleaseNotes_MICROSAR_RTE.htm`, `Rte Peer Review Checklists.xlsm`, `TechnicalReference_Rte.pdf`, `TechnicalReference_RteAnalyzer.pdf`

## Generated code and configuration

- DaVinci `generate/` output shipped with the module.
- AUTOSAR model fragments: `autosar/` (`.arxml`/`.dpa`/`.dcf`).

## Public API

For Vector/Renesas drivers the API is the AUTOSAR-specified set declared in `include/` (e.g. `Init`, `GetVersionInfo`, job APIs) plus callbacks configured in ECUC; the exact set follows the Vector Technical Reference linked below.

## Usage example

```c
/* Typical BSW usage (see Technical Reference for exact API): */
/* EcuM initialises the stack; SW-Cs use services via the RTE. */
Std_ReturnType ret = EcuM_Init(); /* integration startup, simplified */
```

## Dependencies

- Configured through DaVinci/ECUC; initialised by EcuM in the integration startup order.
- Service users reach it via the RTE; error reporting via Det/Dem where applicable.

## Converted documentation

- [AN-ISC-8-1166_RTE_BRE_without_AUTOSAR_OS.pdf](./an-isc-8-1166-rte-bre-without-autosar-os/)
- [TechnicalReference_Rte.pdf](./technicalreference-rte/)
- [TechnicalReference_RteAnalyzer.pdf](./technicalreference-rteanalyzer/)

## Repository location

Repo path: `Rte/` — subfolders present: `autosar/`, `doc/`, `tools/`, `generate/`.
