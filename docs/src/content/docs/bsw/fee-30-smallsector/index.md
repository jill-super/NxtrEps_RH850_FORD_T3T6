---
title: "Flash EEPROM Emulation (Small Sector)"
description: "Fee_30_SmallSector: Flash EEPROM Emulation (SmallSector variant): wear-levelled persistent storage on data flash."
---


import { Badge } from '@astrojs/starlight/components';

# Flash EEPROM Emulation (Small Sector)

Repo directory: `Fee_30_SmallSector/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

Flash EEPROM Emulation (SmallSector variant): wear-levelled persistent storage on data flash.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `Fee_30_SmallSector/src/Fee_30_SmallSector.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (13 entries): `Fee_30_SmallSector.c`, `Fee_30_SmallSector_BlockHandler.c`, `Fee_30_SmallSector_DatasetHandler.c`, `Fee_30_SmallSector_FlsCoordinator.c`, `Fee_30_SmallSector_InstanceHandler.c`, `Fee_30_SmallSector_Layer1_Read.c`, `Fee_30_SmallSector_Layer1_Write.c`, `Fee_30_SmallSector_Layer2_DatasetEraser.c`, `Fee_30_SmallSector_Layer2_InstanceFinder.c`, `Fee_30_SmallSector_Layer2_WriteInstance.c`, `Fee_30_SmallSector_Layer3_ReadManagementBytes.c`, `Fee_30_SmallSector_PartitionHandler.c`, `Fee_30_SmallSector_TaskManager.c`
- `include/` (14 entries): `Fee_30_SmallSector.h`, `Fee_30_SmallSector_BlockHandler.h`, `Fee_30_SmallSector_Cbk.h`, `Fee_30_SmallSector_DatasetHandler.h`, `Fee_30_SmallSector_FlsCoordinator.h`, `Fee_30_SmallSector_InstanceHandler.h`, `Fee_30_SmallSector_Layer1_Read.h`, `Fee_30_SmallSector_Layer1_Write.h`, `Fee_30_SmallSector_Layer2_DatasetEraser.h`, `Fee_30_SmallSector_Layer2_InstanceFinder.h`, `Fee_30_SmallSector_Layer2_WriteInstance.h`, `Fee_30_SmallSector_Layer3_ReadManagementBytes.h`, `Fee_30_SmallSector_PartitionHandler.h`, `Fee_30_SmallSector_TaskManager.h`
- `autosar/` (2 entries): `Fee_30_SmallSector_SafeBSW_pre_Asr4.0.3.arxml`, `Fee_30_SmallSector_bswmd_Asr4.0.3.arxml`
- `make/` (4 entries): `Fee_30_SmallSector_cfg.mak`, `Fee_30_SmallSector_check.mak`, `Fee_30_SmallSector_defs.mak`, `Fee_30_SmallSector_rules.mak`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Fee_30_SmallSector.gpj`, `Integrate.bat`, `IntegrationCopy`
- `doc/` (2 entries): `Fee_30_SmallSector Peer Review Checklists.xlsm`, `TechnicalReference_Fee_30_SmallSector.pdf`

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

- [TechnicalReference_Fee_30_SmallSector.pdf](./technicalreference-fee-30-smallsector/)

## Repository location

Repo path: `Fee_30_SmallSector/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
