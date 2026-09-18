---
title: "Architecture"
description: "ECU hardware, AUTOSAR layering, safety and communication overview."
---

# Architecture

## ECU and vehicle context

- **ECU:** Electric Power Steering controller for the Ford T3T6 platform.
- **MCU:** Renesas RH850 (P1x-C family; see `RenesasMcalSuprt/` and the MCAL layer).
- **Standards:** AUTOSAR 4.x (MICROSAR stack via Vector SIP), ISO 26262 up to ASIL D,
  CAN / CAN-FD (Ford Hi-Speed buses), UDS diagnostics (ISO 14229), XCP calibration.

## Layer map (this site)

```text
Application Software (asw/)        SF* CF* MM* NM* DF* Ford* + AR* platform libs
                                             |  RTE
Complex Device Drivers (cdd/)      CM* MCU/peripheral cfg   ES* sensing/power/motor
                                             |
Basic Software (bsw/)              Vector MICROSAR: Com/Can/Nm/PduR, NvM/Fee/MemIf,
                                   Dcm/Dem, EcuM/EcuC, BswM, Os, Rte, XCP, WdgM/If, IoHwAb
                                             |
MCAL (mcal/)                       Renesas P1x-C/X1x: Mcu Port Dio Spi Fls Wdg
                                             |
Hardware                           RH850 + EPS sensors, gate driver, motor
```

- **ASW** implements steering functions as RTE SW-Cs; shared math/filter/interp
  helpers live in `AR*` platform libraries.
- **CDD (CM*/ES*)** is project-owned code with direct hardware access that does not
  fit a standardised MCAL/BSW module (sensor front-ends, power sequencing, motor paths).
- **BSW** is overwhelmingly Vector-provided and DaVinci-configured; do not hand-edit it.
- **MCAL** is Renesas-provided; configuration comes from the integration ECUC set.
- **Integration** (`_Ford_T3T6_Eps_Impl_A/`) binds everything: `generate/` (RTE/BSW
  output), `autosar/Config` (ECUC/system `.arxml`), GHS projects and CAN databases.

## Safety and diagnostics concept

- Program-flow/checkpoint supervision (`Ford001A_ChkPt`), critical-register verification
  (`CM111A`), core-voltage and clock monitors, shutdown mechanism (`ES108A`),
  loss-of-assist management (`SF049B`) and diagnostic manager (`ES101A`) with
  Dem/Dcm UDS services.
- Persistent data via NvM/Fee; calibration/measurement via XCP; fault-injection hooks
  (`DF001A`) support validation.

## Communication

- Ford Hi-Speed CAN (incl. FD where configured): one gateway SW-C per frame (`MM*`),
  COM/PduR routing, CanTp for UDS, CanNm/ComM for network management, XCP on CAN.
- Databases under `_Ford_T3T6_Eps_Impl_A/autosar/Config/System/` (`.dbc`/`.arxml`/`.cdd`).
