---
title: "Universal Measurement and Calibration Protocol"
description: "Xcp: Universal Measurement and Calibration Protocol stack (with CanXcp transport)."
---


import { Badge } from '@astrojs/starlight/components';

# Universal Measurement and Calibration Protocol

Repo directory: `Xcp/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

Universal Measurement and Calibration Protocol stack (with CanXcp transport).

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `Xcp/src/Xcp.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (1 entries): `Xcp.c`
- `include/` (2 entries): `Xcp.h`, `Xcp_Types.h`
- `autosar/` (3 entries): `Ford`, `GM`, `Xcp_bswmd.arxml`
- `make/` (4 entries): `Xcp_cfg.mak`, `Xcp_check.mak`, `Xcp_defs.mak`, `Xcp_rules.mak`
- `tools/` (5 entries): `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`, `Xcp.gpj`, `templates`
- `doc/` (5 entries): `AN-ISC-8-1169_How_to_add_XCP_PDUs_in_DaVinciConfiguratorPro.pdf`, `TechnicalReference_Xcp.pdf`, `UserManual_AUTOSAR_Calibration.pdf`, `XCP_ReferenceBook_V2.0_EN.pdf`, `Xcp Peer Review Checklists.xlsm`

## Generated code and configuration

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

- [AN-ISC-8-1169_How_to_add_XCP_PDUs_in_DaVinciConfiguratorPro.pdf](./an-isc-8-1169-how-to-add-xcp-pdus-in-davinciconfiguratorpro/)
- [TechnicalReference_Xcp.pdf](./technicalreference-xcp/)
- [UserManual_AUTOSAR_Calibration.pdf](./usermanual-autosar-calibration/)
- [XCP_ReferenceBook_V2.0_EN.pdf](./xcp-referencebook-v2-0-en/)

## Repository location

Repo path: `Xcp/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
