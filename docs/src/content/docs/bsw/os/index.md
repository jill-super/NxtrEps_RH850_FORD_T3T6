---
title: "Operating System"
description: "Os: AUTOSAR OS (Vector MICROSAR OS, SC2/MC ready): tasks, alarms, counters, schedule tables and protection."
---


import { Badge } from '@astrojs/starlight/components';

# Operating System

Repo directory: `Os/` · Layer: `bsw`

<Badge text="Vector-provided · MICROSAR" variant="caution" />

## Purpose and responsibility

AUTOSAR OS (Vector MICROSAR OS, SC2/MC ready): tasks, alarms, counters, schedule tables and protection.

## Origin

**Vector-provided · MICROSAR.** Vector copyright header in `Os/src/Os_AccessCheck.c` (MICROSAR delivery, configured by DaVinci/ECUC).

:::caution[Third-party code — do not hand-edit]
This module is delivered by Vector/Renesas and configured via DaVinci/ECUC. Change the configuration, not the sources. :::

## Key files

- `src/` (43 entries): `Os_AccessCheck.c`, `Os_Alarm.c`, `Os_Application.c`, `Os_Barrier.c`, `Os_Bit.c`, `Os_BitArray.c`, `Os_Core.c`, `Os_Counter.c`, `Os_Deque.c`, `Os_Error.c`, `Os_Event.c`, `Os_Fifo.c`, `Os_Fifo08.c`, `Os_Fifo16.c` (+29 more)
- `include/` (170 entries): `Os.h`, `OsInt.h`, `Os_AccessCheck.h`, `Os_AccessCheckInt.h`, `Os_AccessCheck_Types.h`, `Os_Alarm.h`, `Os_AlarmInt.h`, `Os_Alarm_Types.h`, `Os_Application.h`, `Os_ApplicationInt.h`, `Os_Application_Types.h`, `Os_Barrier.h`, `Os_BarrierInt.h`, `Os_Barrier_Types.h` (+156 more)
- `autosar/` (15 entries): `Os_Rh850_bswmd.arxml`, `Os_Rh850_bswmd_pre.arxml`, `Os_Rh850_bswmd_rec.arxml`, `RH850C1H`, `RH850C1M`, `RH850D1x`, `RH850E1x`, `RH850E1xFCC2`, `RH850F1H`, `RH850F1L`, `RH850F1x`, `RH850P1HC`, `RH850P1M`, `RH850P1MC` (+1 more)
- `make/` (5 entries): `Os_Core.mak`, `Os_cfg.mak`, `Os_check.mak`, `Os_defs.mak`, `Os_rules.mak`
- `tools/` (4 entries): `CreateGHSProject.bat`, `Integrate.bat`, `IntegrationCopy`, `Os.gpj`
- `doc/` (3 entries): `AN-ISC-8-1149_ErrorHook_E_OS_DISABLED_INT.pdf`, `Os Peer Review Checklists.xlsm`, `TechnicalReference_Os.pdf`

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

- [AN-ISC-8-1149_ErrorHook_E_OS_DISABLED_INT.pdf](./an-isc-8-1149-errorhook-e-os-disabled-int/)
- [TechnicalReference_Os.pdf](./technicalreference-os/)

## Repository location

Repo path: `Os/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `make/`.
