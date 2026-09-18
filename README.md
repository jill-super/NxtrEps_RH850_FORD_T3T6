# Electric Power Steering (EPS) System for Ford T3T6

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Language: C](https://img.shields.io/badge/Language-C-blue.svg)](.)
![AUTOSAR 4.x](https://img.shields.io/badge/AUTOSAR-4.x-orange.svg)
![ISO 26262 ASIL D](https://img.shields.io/badge/Safety-ASIL_D-red.svg)
![MCU: Renesas RH850](https://img.shields.io/badge/MCU-Renesas_RH850-lightgrey.svg)
[![Docs: Astro Starlight](https://img.shields.io/badge/Docs-Astro_Starlight-ff5d01.svg)](docs/)

Complete **Electric Power Steering (EPS)** software for the **Ford T3T6**
platform: AUTOSAR-layered C code for the **Renesas RH850**, built with the
**Green Hills MULTI** toolchain and the **Vector MICROSAR** (DaVinci/SIP) stack.

## Table of contents

- [Overview](#overview)
- [Repository structure](#repository-structure)
- [AUTOSAR layers](#autosar-layers)
- [Module catalogue](#module-catalogue)
- [Vector vs custom](#vector-vs-custom)
- [Build instructions](#build-instructions)
- [Documentation site](#documentation-site)
- [Contributing](#contributing)
- [License](#license)

## Overview

Key characteristics:

- **Microcontroller**: Renesas RH850 (P1x-C family).
- **Software standard**: AUTOSAR 4.x, implemented with Vector MICROSAR basic
  software, RTE and DaVinci configuration.
- **Functional safety**: developed for ISO 26262 up to ASIL D (checkpoint
  supervision, critical-register verification, shutdown paths, loss-of-assist
  management).
- **Communication**: Ford Hi-Speed CAN (incl. CAN-FD where configured), UDS
  diagnostics (ISO 14229) via Dcm/Dem + CanTp, XCP measurement/calibration.
- **Functionality**: torque assist, return, damping, end-of-travel and power
  limiting, motor-current control, sensor plausibility chains and Ford
  message gatewaying.

## Repository structure

```text
<repo root>/
├── SF* / CF* / MM* / NM* / DF* / AR* / Ford*   # Application Software (ASW)
├── CM* / ES*                                   # Complex Device Drivers (CDD)
├── Can* / Com* / Dcm / Dem / NvM / Os / Rte …  # Vector MICROSAR BSW
├── Mcu / Port / Dio / Spi / Fls / Wdg          # Renesas MCAL
├── TL*/                                        # Host tools (compiler, IDE, generators)
├── _Ford_T3T6_Eps_Impl_A/                      # Top-level ECU integration
├── _Ford_T3T6_Eps_Design_ApplSwArch_A/         # Application architecture design
├── VectorBswSuprt/ / RenesasMcalSuprt/         # Vendor support bundles
├── docs/                                       # Documentation site (Astro v7 + Starlight)
├── LICENSE                                     # MIT licence (project-owned content)
└── README.md                                   # This file
```

> The documentation site source lives entirely in [`docs/`](docs/) — that
> folder is the Astro project root (`docs/package.json`,
> `docs/astro.config.mjs`, `docs/src/content/docs/`). Nothing outside `docs/`
> belongs to the site, and the site build never modifies the C code, tools or
> configuration.

Each module folder typically contains `src/`, `include/`, `autosar/`, `doc/`,
`tools/` (contracts, generation output, DataDict databooks) and `make/`
fragments. Binary design documents under `doc/` are summarised per module in
the docs site.

## AUTOSAR layers

| Layer | Prefixes / folders | Content | Origin |
| --- | --- | --- | --- |
| Application Software (ASW) | `SF*`, `CF*`, `MM*`, `NM*`, `DF*`, `Ford*`, `AR*` | Steering features, Ford customer functions, CAN message gateways, manufacturing/service SW-Cs, test hooks, shared platform libraries | Custom (Nexteer in-house) |
| Complex Device Drivers (CDD) | `CM*`, `ES*` | MCU/peripheral configuration and diagnostics, EPS sensing, power, thermal and motor-control services with direct hardware access | Custom (Nexteer in-house) |
| Basic Software (BSW) | `Can*`, `Com*`, `Dcm`, `Dem`, `Det`, `EcuC/M`, `NvM`, `Fee*`, `MemIf`, `PduR`, `Nm`, `Xcp`, `BswM`, `WdgM/If`, `Os`, `Rte`, `IoHwAb` | Vector MICROSAR communication, memory, system, diagnostics, OS/RTE stacks and ECU abstraction | Vector-provided (DaVinci-configured) |
| MCAL | `Mcu`, `Port`, `Dio`, `Spi`, `Fls`, `Wdg`, `RenesasMcalSuprt` | Renesas P1x-C/X1x microcontroller drivers and support files | Renesas-provided |
| Tools | `TL*` | Green Hills compiler/IDE, DaVinci data, RTE generator, checkers, Python runtime, DataDict toolchain | Third-party / project tooling |
| Integration | `_Ford_T3T6_Eps_*`, `VectorBswSuprt`, `CM012A_*_Design` | Generated RTE/BSW code, ECUC/system configuration, GHS projects, linker scripts, CAN databases | Projectconfig + vendor bundles |

## Module catalogue

207 top-level modules. **Component** is the human-readable long name expanded from
the directory name (abbreviations resolved, e.g. `MM065A_FordMsg217BusHiSpd_Impl`
→ “Ford Message 217 — High-Speed Bus”); the **Module** column holds the exact repo
directory name. The **Docs page** column links to the module's documentation source
(rendered by the site in [`docs/`](docs/)); the **Doc sources** column counts
convertible binary documents (`.doc`/`.docx`/`.pdf` plus `doc/`-level
`.txt`) inventoried for that module.

<details>
<summary><strong>Application Software (ASW)</strong> — 105 modules (click to expand)</summary>

| Component | Module | Origin | Doc sources | Docs page |
| --- | --- | --- | --- | --- |
| Nexteer Math Library (AR100A) | `AR100A_NxtrMath_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/ar100a-nxtrmath-impl/) |
| Nexteer Interpolation (AR101A) | `AR101A_NxtrIntrpn_Impl` | Custom | 1 | [docs](docs/src/content/docs/asw/ar101a-nxtrintrpn-impl/) |
| Nexteer Time (AR102B) | `AR102B_NxtrTi_Impl` | Custom | 1 | [docs](docs/src/content/docs/asw/ar102b-nxtrti-impl/) |
| Nexteer Fixed Point (AR103A) | `AR103A_NxtrFixdPt_Impl` | Custom | 1 | [docs](docs/src/content/docs/asw/ar103a-nxtrfixdpt-impl/) |
| Nexteer Filter (AR104A) | `AR104A_NxtrFil_Impl` | Custom | 1 | [docs](docs/src/content/docs/asw/ar104a-nxtrfil-impl/) |
| AUTOSAR support types (AR200A) | `AR200A_ArSuprt_Impl` | Custom | 0 | [docs](docs/src/content/docs/asw/ar200a-arsuprt-impl/) |
| Compiler support types (AR201A) | `AR201A_ArCplrSuprt_Impl` | Custom | 0 | [docs](docs/src/content/docs/asw/ar201a-arcplrsuprt-impl/) |
| Microcontroller support library (AR202A) | `AR202A_MicroCtrlrSuprt_Impl` | Custom | 3 | [docs](docs/src/content/docs/asw/ar202a-microctrlrsuprt-impl/) |
| Motor Control Manager (AR300A) | `AR300A_MotCtrlMgr_Impl` | Custom | 3 | [docs](docs/src/content/docs/asw/ar300a-motctrlmgr-impl/) |
| Inter-Micro Communication Arbitration (AR350A) | `AR350A_ImcArbn_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/ar350a-imcarbn-impl/) |
| Nexteer Startup (AR400A) | `AR400A_NxtrStrtUp_Impl` | Custom | 1 | [docs](docs/src/content/docs/asw/ar400a-nxtrstrtup-impl/) |
| Nexteer Development Error Tracer (AR998A) | `AR998A_NxtrDet_Impl` | Custom | 3 | [docs](docs/src/content/docs/asw/ar998a-nxtrdet-impl/) |
| Architecture global parameters (AR999A) | `AR999A_ArchGlbPrm_Impl` | Custom | 0 | [docs](docs/src/content/docs/asw/ar999a-archglbprm-impl/) |
| Ford System State (CF052A) | `CF052A_FordSysSt_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/cf052a-fordsysst-impl/) |
| Ford Command Arbitration (CF065A) | `CF065A_FordCmdArbn_Impl` | Custom | 0 | [docs](docs/src/content/docs/asw/cf065a-fordcmdarbn-impl/) |
| Ford Handwheel Torque Command Overall Limiter (CF067A) | `CF067A_FordHwTqCmdOvrlLimr_Impl` | Custom | 1 | [docs](docs/src/content/docs/asw/cf067a-fordhwtqcmdovrllimr-impl/) |
| Ford Handwheel Torque Coding (CF076A) | `CF076A_FordHwTqCdng_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/cf076a-fordhwtqcdng-impl/) |
| Ford Black Box Interface Common (CF110A) | `CF110A_FordBlaBoxIfCmn_Impl` | Custom | 0 | [docs](docs/src/content/docs/asw/cf110a-fordblaboxifcmn-impl/) |
| Ford Black Box Interface Component 1 (CF111A) | `CF111A_FordBlaBoxIfCmp1_Impl` | Custom | 0 | [docs](docs/src/content/docs/asw/cf111a-fordblaboxifcmp1-impl/) |
| Ford Black Box Interface Component 2 (CF112A) | `CF112A_FordBlaBoxIfCmp2_Impl` | Custom | 0 | [docs](docs/src/content/docs/asw/cf112a-fordblaboxifcmp2-impl/) |
| Fault Injection (DF001A) | `DF001A_FltInj_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/df001a-fltinj-impl/) |
| Swp test support (DF002A) | `DF002A_Swp_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/df002a-swp-impl/) |
| Checkpoint monitor (Ford001A) | `Ford001A_ChkPt_Impl` | Custom | 0 | [docs](docs/src/content/docs/asw/ford001a-chkpt-impl/) |
| Ford Message 07D — High-Speed Bus (MM052A) | `MM052A_FordMsg07DBusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm052a-fordmsg07dbushispd-impl/) |
| Ford Message 083 — High-Speed Bus (MM054A) | `MM054A_FordMsg083BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm054a-fordmsg083bushispd-impl/) |
| Ford Message 091 — High-Speed Bus (MM056A) | `MM056A_FordMsg091BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm056a-fordmsg091bushispd-impl/) |
| Ford Message 215 — High-Speed Bus (MM057A) | `MM057A_FordMsg215BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm057a-fordmsg215bushispd-impl/) |
| Ford Message 167 — High-Speed Bus (MM059A) | `MM059A_FordMsg167BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm059a-fordmsg167bushispd-impl/) |
| Ford Message 202 — High-Speed Bus (MM061A) | `MM061A_FordMsg202BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm061a-fordmsg202bushispd-impl/) |
| Ford Message 213 — High-Speed Bus (MM063A) | `MM063A_FordMsg213BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm063a-fordmsg213bushispd-impl/) |
| Ford Message 216 — High-Speed Bus (MM064A) | `MM064A_FordMsg216BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm064a-fordmsg216bushispd-impl/) |
| Ford Message 217 — High-Speed Bus (MM065A) | `MM065A_FordMsg217BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm065a-fordmsg217bushispd-impl/) |
| Ford Message 230 — High-Speed Bus (MM066A) | `MM066A_FordMsg230BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm066a-fordmsg230bushispd-impl/) |
| Ford Message 414 — High-Speed Bus (MM070A) | `MM070A_FordMsg414BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm070a-fordmsg414bushispd-impl/) |
| Ford Message 3B3 — High-Speed Bus (MM072A) | `MM072A_FordMsg3B3BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm072a-fordmsg3b3bushispd-impl/) |
| Ford Message 3CA — High-Speed Bus (MM073A) | `MM073A_FordMsg3CABusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm073a-fordmsg3cabushispd-impl/) |
| Ford Message 3D3 — High-Speed Bus (MM074A) | `MM074A_FordMsg3D3BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm074a-fordmsg3d3bushispd-impl/) |
| Ford Message 3D7 — High-Speed Bus (MM075A) | `MM075A_FordMsg3D7BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm075a-fordmsg3d7bushispd-impl/) |
| Ford Message 40A — High-Speed Bus (MM076A) | `MM076A_FordMsg40ABusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm076a-fordmsg40abushispd-impl/) |
| Ford Message 415 — High-Speed Bus (MM077A) | `MM077A_FordMsg415BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm077a-fordmsg415bushispd-impl/) |
| Ford Message 41A — High-Speed Bus (MM078A) | `MM078A_FordMsg41ABusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm078a-fordmsg41abushispd-impl/) |
| Ford Message 41E — High-Speed Bus (MM079A) | `MM079A_FordMsg41EBusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm079a-fordmsg41ebushispd-impl/) |
| Ford Message 430 — High-Speed Bus (MM081A) | `MM081A_FordMsg430BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm081a-fordmsg430bushispd-impl/) |
| Ford Message 443 — High-Speed Bus (MM086A) | `MM086A_FordMsg443BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm086a-fordmsg443bushispd-impl/) |
| Ford Message 4B0 — High-Speed Bus (MM089A) | `MM089A_FordMsg4B0BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm089a-fordmsg4b0bushispd-impl/) |
| Ford Message 459 — High-Speed Bus (MM090A) | `MM090A_FordMsg459BusHiSpd_Impl` | Custom | 0 | [docs](docs/src/content/docs/asw/mm090a-fordmsg459bushispd-impl/) |
| Ford Message 47A — High-Speed Bus (MM092A) | `MM092A_FordMsg47ABusHiSpd_Impl` | Custom | 0 | [docs](docs/src/content/docs/asw/mm092a-fordmsg47abushispd-impl/) |
| Ford Message 077 — High-Speed Bus (MM124A) | `MM124A_FordMsg077BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm124a-fordmsg077bushispd-impl/) |
| Ford Message 2FD — High-Speed Bus (MM134A) | `MM134A_FordMsg2FDBusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm134a-fordmsg2fdbushispd-impl/) |
| Ford Message 417 — High-Speed Bus (MM518A) | `MM518A_FordMsg417BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm518a-fordmsg417bushispd-impl/) |
| Ford Message 5B5 — High-Speed Bus (MM519A) | `MM519A_FordMsg5B5BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm519a-fordmsg5b5bushispd-impl/) |
| Ford Message 07E — High-Speed Bus (MM531A) | `MM531A_FordMsg07EBusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm531a-fordmsg07ebushispd-impl/) |
| Ford Message 082 — High-Speed Bus (MM532A) | `MM532A_FordMsg082BusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm532a-fordmsg082bushispd-impl/) |
| Ford Message 3CC — High-Speed Bus (MM533A) | `MM533A_FordMsg3CCBusHiSpd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/mm533a-fordmsg3ccbushispd-impl/) |
| Common Manufacturing Service (NM001A) | `NM001A_CmnMfgSrv_Impl` | Custom | 4 | [docs](docs/src/content/docs/asw/nm001a-cmnmfgsrv-impl/) |
| Nexteer Software IDs (NM003A) | `NM003A_NxtrSwIds_Impl` | Custom | 0 | [docs](docs/src/content/docs/asw/nm003a-nxtrswids-impl/) |
| Nexteer Calibration IDs (NM004A) | `NM004A_NxtrCalIds_Impl` | Custom | 0 | [docs](docs/src/content/docs/asw/nm004a-nxtrcalids-impl/) |
| Motor Velocity Control (NM100A) | `NM100A_MotVelCtrl_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/nm100a-motvelctrl-impl/) |
| Assist (SF001A) | `SF001A_Assi_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf001a-assi-impl/) |
| Return (SF002A) | `SF002A_Rtn_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf002a-rtn-impl/) |
| Damping (SF003A) | `SF003A_Dampg_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf003a-dampg-impl/) |
| Assist Sum Limit (SF004B) | `SF004B_AssiSumLim_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf004b-assisumlim-impl/) |
| Steering Output Control (SF005A) | `SF005A_StOutpCtrl_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf005a-stoutpctrl-impl/) |
| Torque Estimation (SF006A) | `SF006A_TEstimn_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf006a-testimn-impl/) |
| System Friction Learning (SF007A) | `SF007A_SysFricLrng_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf007a-sysfriclrng-impl/) |
| Duty Cycle Thermal Protection (SF009A) | `SF009A_DutyCycThermProtn_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf009a-dutycycthermprotn-impl/) |
| End of Travel Learning (SF011A) | `SF011A_EotLrng_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf011a-eotlrng-impl/) |
| Hysteresis Compensation (SF012A) | `SF012A_HysCmp_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf012a-hyscmp-impl/) |
| Inertia Compensation Velocity (SF014A) | `SF014A_InertiaCmpVel_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf014a-inertiacmpvel-impl/) |
| Vehicle Speed Limiter (SF016A) | `SF016A_VehSpdLimr_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf016a-vehspdlimr-impl/) |
| High Load Stall Limiter (SF017A) | `SF017A_HiLoadStallLimr_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf017a-hiloadstalllimr-impl/) |
| End of Travel Protection (SF018A) | `SF018A_EotProtn_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf018a-eotprotn-impl/) |
| Power Limiter (SF019B) | `SF019B_PwrLimr_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf019b-pwrlimr-impl/) |
| Position Tracking Servo (SF020B) | `SF020B_PosnTrakgServo_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf020b-posntrakgservo-impl/) |
| Tuning Selection Authority (SF023A) | `SF023A_TunSelnAuthy_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf023a-tunselnauthy-impl/) |
| End of Travel Protection Firewall (SF027A) | `SF027A_EotProtnFwl_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf027a-eotprotnfwl-impl/) |
| Assist High Frequency (SF028A) | `SF028A_AssiHiFrq_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf028a-assihifrq-impl/) |
| Stability Compensation (SF029A) | `SF029A_StabyCmp_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf029a-stabycmp-impl/) |
| Motor Torque Command Scaling (SF032A) | `SF032A_MotTqCmdSca_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf032a-mottqcmdsca-impl/) |
| Vehicle Signal Coding (SF033A) | `SF033A_VehSigCdng_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf033a-vehsigcdng-impl/) |
| Assist Path Sum (SF034B) | `SF034B_AssiPahSum_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf034b-assipahsum-impl/) |
| Damping Path Sum (SF035B) | `SF035B_DampgPahSum_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf035b-dampgpahsum-impl/) |
| Return Path Firewall (SF036A) | `SF036A_RtnPahFwl_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf036a-rtnpahfwl-impl/) |
| Limiter Coding (SF038A) | `SF038A_LimrCdng_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf038a-limrcdng-impl/) |
| Motor Velocity (SF040A) | `SF040A_MotVel_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf040a-motvel-impl/) |
| Compliance Error (SF041A) | `SF041A_CmplncErr_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf041a-cmplncerr-impl/) |
| Handwheel Angle Sensorless (SF042A) | `SF042A_HwAgSnsrls_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf042a-hwagsnsrls-impl/) |
| Handwheel Angle System Arbitration (SF045A) | `SF045A_HwAgSysArbn_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf045a-hwagsysarbn-impl/) |
| Torque Loss of Assist (SF048A) | `SF048A_TqLoa_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf048a-tqloa-impl/) |
| Loss of Assist Manager (SF049B) | `SF049B_LoaMgr_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf049b-loamgr-impl/) |
| Motor Torque Transitional Damping (SF050A) | `SF050A_MotTqTranlDampg_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf050a-mottqtranldampg-impl/) |
| Driver Torque Estimation (SF056A) | `SF056A_DrvrTqEstimn_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf056a-drvrtqestimn-impl/) |
| System Performance Status (SF059A) | `SF059A_SysPrfmncSts_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf059a-sysprfmncsts-impl/) |
| Dual Controller Output Manager (SF062B) | `SF062B_DualCtrlrOutpMgr_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf062b-dualctrlroutpmgr-impl/) |
| Inter-Micro Communication Signal Arbitration (SF063A) | `SF063A_ImcSigArbn_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf063a-imcsigarbn-impl/) |
| Motor Quadrant Detection (SF101A) | `SF101A_MotQuadDetn_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf101a-motquaddetn-impl/) |
| Motor Control Parameters Estimation (SF102A) | `SF102A_MotCtrlPrmEstimn_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf102a-motctrlprmestimn-impl/) |
| Motor Reference Model (SF103A) | `SF103A_MotRefMdl_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf103a-motrefmdl-impl/) |
| Motor Current Regulator Configuration (SF104A) | `SF104A_MotCurrRegCfg_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf104a-motcurrregcfg-impl/) |
| Motor Current Regulator Voltage Limiter (SF105A) | `SF105A_MotCurrRegVltgLimr_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf105a-motcurrregvltglimr-impl/) |
| Motor Ripple Cogging Configuration (SF106A) | `SF106A_MotRplCoggCfg_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf106a-motrplcoggcfg-impl/) |
| Motor Ripple Cogging Command (SF107A) | `SF107A_MotRplCoggCmd_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf107a-motrplcoggcmd-impl/) |
| Motor Current Peak Estimation (SF108A) | `SF108A_MotCurrPeakEstimn_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf108a-motcurrpeakestimn-impl/) |
| Electrical Power Consumption (SF109A) | `SF109A_ElecPwrCns_Impl` | Custom | 2 | [docs](docs/src/content/docs/asw/sf109a-elecpwrcns-impl/) |
| System global parameters (SF999A) | `SF999A_SysGlbPrm_Impl` | Custom | 0 | [docs](docs/src/content/docs/asw/sf999a-sysglbprm-impl/) |

</details>
<details>
<summary><strong>Complex Device Drivers (CDD)</strong> — 54 modules (click to expand)</summary>

| Component | Module | Origin | Doc sources | Docs page |
| --- | --- | --- | --- | --- |
| Exception Handling (CM101B) | `CM101B_ExcpnHndlg_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm101b-excpnhndlg-impl/) |
| Flash Memory (CM102B) | `CM102B_FlsMem_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm102b-flsmem-impl/) |
| RAM memory (CM103B) | `CM103B_RamMem_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm103b-rammem-impl/) |
| ECM Output and Diagnostics (CM104B) | `CM104B_EcmOutpAndDiagc_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm104b-ecmoutpanddiagc-impl/) |
| MCU Core Configuration and Diagnostics (CM106B) | `CM106B_McuCoreCfgAndDiagc_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm106b-mcucorecfganddiagc-impl/) |
| Guard Configuration and Diagnostics (CM107B) | `CM107B_GuardCfgAndDiagc_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm107b-guardcfganddiagc-impl/) |
| Clock Configuration and Monitor (CM109B) | `CM109B_ClkCfgAndMon_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm109b-clkcfgandmon-impl/) |
| Critical register verification (CM111A) | `CM111A_VrfyCritReg_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm111a-vrfycritreg-impl/) |
| Core Voltage Monitor (CM112B) | `CM112B_CoreVltgMonr_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm112b-corevltgmonr-impl/) |
| DMA Configuration and Use (CM201A) | `CM201A_DmaCfgAndUse_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm201a-dmacfganduse-impl/) |
| ADCF 0 Configuration and Use (CM301A) | `CM301A_Adcf0CfgAndUse_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm301a-adcf0cfganduse-impl/) |
| ADCF 1 Configuration and Use (CM321A) | `CM321A_Adcf1CfgAndUse_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm321a-adcf1cfganduse-impl/) |
| Handwheel Torque 1 Measurement (CM660A) | `CM660A_HwTq1Meas_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm660a-hwtq1meas-impl/) |
| Handwheel Angle 1 Measurement (CM670A) | `CM670A_HwAg1Meas_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm670a-hwag1meas-impl/) |
| Handwheel Torque 8 Measurement (CM690D) | `CM690D_HwTq8Meas_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm690d-hwtq8meas-impl/) |
| UART 0 Configuration and Use (CM760A) | `CM760A_Uart0CfgAndUse_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm760a-uart0cfganduse-impl/) |
| UART 1 Configuration and Use (CM765A) | `CM765A_Uart1CfgAndUse_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm765a-uart1cfganduse-impl/) |
| GTM Configuration and Use (CM770A) | `CM770A_GtmCfgAndUse_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm770a-gtmcfganduse-impl/) |
| Sync CRC (CM800A) | `CM800A_SyncCrc_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/cm800a-synccrc-impl/) |
| MCU Diagnostics (ES002A) | `ES002A_McuDiagc_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es002a-mcudiagc-impl/) |
| Power Disconnect (ES003C) | `ES003C_PwrDiscnct_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es003c-pwrdiscnct-impl/) |
| Power Up Sequence (ES004A) | `ES004A_PwrUpSeq_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es004a-pwrupseq-impl/) |
| Tmpl monitor (ES005C) | `ES005C_TmplMonr_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es005c-tmplmonr-impl/) |
| NVRAM proxy service (ES006A) | `ES006A_NvM_Impl` | Custom | 1 | [docs](docs/src/content/docs/cdd/es006a-nvm-impl/) |
| Power Supply (ES008A) | `ES008A_PwrSply_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es008a-pwrsply-impl/) |
| Dual ECU Identification (ES011A) | `ES011A_DualEcuIdn_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es011a-dualecuidn-impl/) |
| System State Mode (ES100A) | `ES100A_SysStMod_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es100a-sysstmod-impl/) |
| Diagnostics Manager (ES101A) | `ES101A_DiagcMgr_Impl` | Custom | 3 | [docs](docs/src/content/docs/cdd/es101a-diagcmgr-impl/) |
| Polarity Configuration (ES102A) | `ES102A_PolarityCfg_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es102a-polaritycfg-impl/) |
| XCP Interface (ES104A) | `ES104A_XcpIf_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es104a-xcpif-impl/) |
| Shutdown Mechanism (ES108A) | `ES108A_ShtdwnMech_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es108a-shtdwnmech-impl/) |
| Current Measurement (ES200B) | `ES200B_CurrMeas_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es200b-currmeas-impl/) |
| Current Measurement Arbitration (ES208A) | `ES208A_CurrMeasArbn_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es208a-currmeasarbn-impl/) |
| Current Measurement Correlation (ES209B) | `ES209B_CurrMeasCorrln_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es209b-currmeascorrln-impl/) |
| ECU Temperature Measurement (ES210A) | `ES210A_EcuTMeas_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es210a-ecutmeas-impl/) |
| Handwheel Torque 9 Measurement (ES224A) | `ES224A_HwTq9Meas_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es224a-hwtq9meas-impl/) |
| Handwheel Torque 10 Measurement (ES225A) | `ES225A_HwTq10Meas_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es225a-hwtq10meas-impl/) |
| Handwheel Torque Arbitration (ES228C) | `ES228C_HwTqArbn_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es228c-hwtqarbn-impl/) |
| Handwheel Torque Correlation (ES229C) | `ES229C_HwTqCorrln_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es229c-hwtqcorrln-impl/) |
| Handwheel Angle Arbitration (ES238B) | `ES238B_HwAgArbn_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es238b-hwagarbn-impl/) |
| Handwheel Angle Correlation (ES239B) | `ES239B_HwAgCorrln_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es239b-hwagcorrln-impl/) |
| Motor Angle 2 Measurement (ES241A) | `ES241A_MotAg2Meas_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es241a-motag2meas-impl/) |
| Motor Angle 5 Measurement (ES242A) | `ES242A_MotAg5Meas_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es242a-motag5meas-impl/) |
| Motor Angle 6 Measurement (ES243A) | `ES243A_MotAg6Meas_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es243a-motag6meas-impl/) |
| Motor Angle Compensation (ES247A) | `ES247A_MotAgCmp_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es247a-motagcmp-impl/) |
| Motor Angle Arbitration (ES248A) | `ES248A_MotAgArbn_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es248a-motagarbn-impl/) |
| Motor Angle Correlation (ES249A) | `ES249A_MotAgCorrln_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es249a-motagcorrln-impl/) |
| Battery Voltage (ES250B) | `ES250B_BattVltg_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es250b-battvltg-impl/) |
| Battery Voltage Correlation (ES259B) | `ES259B_BattVltgCorrln_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es259b-battvltgcorrln-impl/) |
| Motor Angle Software Calibration (ES280A) | `ES280A_MotAgSwCal_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es280a-motagswcal-impl/) |
| Sine Voltage Generation (ES300A) | `ES300A_SinVltgGenn_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es300a-sinvltggenn-impl/) |
| Gate Driver 0 Control (ES311A) | `ES311A_GateDrv0Ctrl_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es311a-gatedrv0ctrl-impl/) |
| Tuning Selection Management (ES400A) | `ES400A_TunSelnMngt_Impl` | Custom | 2 | [docs](docs/src/content/docs/cdd/es400a-tunselnmngt-impl/) |
| Electrical global parameters (ES999A) | `ES999A_ElecGlbPrm_Impl` | Custom | 1 | [docs](docs/src/content/docs/cdd/es999a-elecglbprm-impl/) |

</details>
<details>
<summary><strong>Basic Software (BSW)</strong> — 26 modules (click to expand)</summary>

| Component | Module | Origin | Doc sources | Docs page |
| --- | --- | --- | --- | --- |
| BSW Mode Manager | `BswM` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/bswm/) |
| CAN Driver | `Can` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/can/) |
| CAN Interface | `CanIf` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/canif/) |
| CAN Network Management | `CanNm` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/cannm/) |
| CAN State Manager | `CanSm` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/cansm/) |
| CAN Transport Protocol | `CanTp` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/cantp/) |
| CAN XCP Transport | `CanXcp` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/canxcp/) |
| Communication | `Com` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/com/) |
| Communication Manager | `ComM` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/comm/) |
| CRC Library | `Crc` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/crc/) |
| Diagnostic Communication Manager | `Dcm` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/dcm/) |
| Diagnostic Event Manager | `Dem` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/dem/) |
| Development Error Tracer | `Det` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/det/) |
| ECU Configuration | `EcuC` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/ecuc/) |
| ECU State Manager | `EcuM` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/ecum/) |
| Flash EEPROM Emulation (Small Sector) | `Fee_30_SmallSector` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/fee-30-smallsector/) |
| I/O Hardware Abstraction | `IoHwAb` | Vector customised | 1 | [docs](docs/src/content/docs/bsw/iohwab/) |
| Memory Abstraction Interface | `MemIf` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/memif/) |
| Network Management | `Nm` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/nm/) |
| NVRAM Manager | `NvM` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/nvm/) |
| Operating System | `Os` | Vector-provided | 2 | [docs](docs/src/content/docs/bsw/os/) |
| PDU Router | `PduR` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/pdur/) |
| Run-Time Environment | `Rte` | Vector-provided | 3 | [docs](docs/src/content/docs/bsw/rte/) |
| Watchdog Interface | `WdgIf` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/wdgif/) |
| Watchdog Manager | `WdgM` | Vector-provided | 1 | [docs](docs/src/content/docs/bsw/wdgm/) |
| Universal Measurement and Calibration Protocol | `Xcp` | Vector-provided | 4 | [docs](docs/src/content/docs/bsw/xcp/) |

</details>
<details>
<summary><strong>Microcontroller Abstraction (MCAL)</strong> — 7 modules (click to expand)</summary>

| Component | Module | Origin | Doc sources | Docs page |
| --- | --- | --- | --- | --- |
| Digital Input/Output Driver | `Dio` | Renesas-provided | 3 | [docs](docs/src/content/docs/mcal/dio/) |
| Flash Driver | `Fls` | Renesas-provided | 3 | [docs](docs/src/content/docs/mcal/fls/) |
| Microcontroller Unit Driver | `Mcu` | Renesas-provided | 3 | [docs](docs/src/content/docs/mcal/mcu/) |
| Port Driver | `Port` | Renesas-provided | 3 | [docs](docs/src/content/docs/mcal/port/) |
| Renesas MCAL Support | `RenesasMcalSuprt` | Custom | 22 | [docs](docs/src/content/docs/mcal/renesasmcalsuprt/) |
| Serial Peripheral Interface Driver | `Spi` | Renesas-provided | 3 | [docs](docs/src/content/docs/mcal/spi/) |
| Watchdog Driver | `Wdg` | Renesas-provided | 3 | [docs](docs/src/content/docs/mcal/wdg/) |

</details>
<details>
<summary><strong>Tools and host utilities</strong> — 11 modules (click to expand)</summary>

| Component | Module | Origin | Doc sources | Docs page |
| --- | --- | --- | --- | --- |
| Component RTE Generator (TL101A) | `TL101A_CptRteGen` | Host tool | 1 | [docs](docs/src/content/docs/tools/tl101a-cptrtegen/) |
| DaVinci Configurator data (TL102A) | `TL102A_Davinci` | Host tool | 0 | [docs](docs/src/content/docs/tools/tl102a-davinci/) |
| AUTOSAR Run-Time Test tooling (TL105A) | `TL105A_Artt` | Host tool | 0 | [docs](docs/src/content/docs/tools/tl105a-artt/) |
| Software Component support scripts (TL109A) | `TL109A_SwcSuprt` | Host tool | 1 | [docs](docs/src/content/docs/tools/tl109a-swcsuprt/) |
| Common checks tool (TL111A) | `TL111A_CmnChksTool` | Host tool | 0 | [docs](docs/src/content/docs/tools/tl111a-cmnchkstool/) |
| Python host environment (TL112A) | `TL112A_Python` | Host tool | 1 | [docs](docs/src/content/docs/tools/tl112a-python/) |
| Software option switch (TL116A) | `TL116A_SwOptnSwt` | Host tool | 0 | [docs](docs/src/content/docs/tools/tl116a-swoptnswt/) |
| Data dictionary toolchain (TL117A) | `TL117A_DataDict` | Host tool | 0 | [docs](docs/src/content/docs/tools/tl117a-datadict/) |
| Green Hills compiler toolchain (TL120A) | `TL120A_Cplr` | Host tool | 14 | [docs](docs/src/content/docs/tools/tl120a-cplr/) |
| Green Hills IDE support (TL121A) | `TL121A_Ide` | Host tool | 8 | [docs](docs/src/content/docs/tools/tl121a-ide/) |
| Memory metrics tooling (TL124A) | `TL124A_MemMtrc` | Host tool | 0 | [docs](docs/src/content/docs/tools/tl124a-memmtrc/) |

</details>
<details>
<summary><strong>Integration and system config</strong> — 4 modules (click to expand)</summary>

| Component | Module | Origin | Doc sources | Docs page |
| --- | --- | --- | --- | --- |
| Ford T3 MCU Configuration (design) | `CM012A_FordT3McuCfg_Design` | Integration | 0 | [docs](docs/src/content/docs/integration/cm012a-fordt3mcucfg-design/) |
| Vector BSW Support | `VectorBswSuprt` | Vector-provided | 5 | [docs](docs/src/content/docs/integration/vectorbswsuprt/) |
| Ford T3T6 EPS Application Software Architecture (design) | `_Ford_T3T6_Eps_Design_ApplSwArch_A` | Integration | 0 | [docs](docs/src/content/docs/integration/ford-t3t6-eps-design-applswarch-a/) |
| Ford T3T6 EPS Implementation (top-level integration) | `_Ford_T3T6_Eps_Impl_A` | Integration | 28 | [docs](docs/src/content/docs/integration/ford-t3t6-eps-impl-a/) |

</details>

## Vector vs custom

Every module page in the docs site carries an origin badge:

- **Vector-provided** — third-party BSW from the Vector SIP/MICROSAR delivery,
  configured with DaVinci/ECUC. Do not hand-edit; change the configuration.
- **Vector customised** — Vector template with project-specific mapping (only
  `IoHwAb`, mapped in `_Ford_T3T6_Eps_Impl_A/src/IoHwAb_30.c`).
- **Renesas-provided** — Renesas P1x-C/X1x MCAL drivers and support files.
- **Custom** — project-owned SW-Cs, complex drivers, services and platform
  libraries. Note: RTE/generator headers inside `tools/` may still mention
  Vector — that identifies the *generator*, not the owner.
- **Host tool / Integration** — build-time tooling or aggregated configuration.

Origin was determined from primary source copyright headers per module; the
evidence file is quoted on each module page
(see also `docs/src/content/docs/general/origin-guide/`).

## Build instructions

Supported path is Windows + Green Hills MULTI (shipped in-tree):

1. Open `_Ford_T3T6_Eps_Impl_A/tools/LaunchProject.bat` (or the `.gpj`
   projects: `T3T6.gpj`, `src.gpj`, `generate.gpj`, `include.gpj`,
   `scripts.gpj`) in the MULTI IDE from `TL120A_Cplr/` + `TL121A_Ide/`.
2. Generate: DaVinci/SIP configuration (`TL102A_Davinci`, `VectorBswSuprt`,
   `_Ford_T3T6_Eps_Impl_A/autosar/Config/`) → `generate/` (RTE/BSW output,
   `MemMap`/`SchM`, A2L); per-SW-C RTE contracts via `TL101A_CptRteGen`;
   calibration artefacts from the DataDict `.m` databooks
   (`<module>/tools/DataDict/`, merged under
   `_Ford_T3T6_Eps_Impl_A/tools/DataDict/`).
3. Build each BSW module through its `make/*_{cfg,defs,check,rules}.mak`
   fragments (Vector AUTOSAR makefile interface) and link with the
   `dr7f701373.ld`/`.dvf` scripts to `output/T3T6.elf`.
4. Flash the image onto the Renesas RH850 target and validate with the CANoe /
   CANape setups under `_Ford_T3T6_Eps_Impl_A/tools/` (archives) and the
   `.dbc`/`.arxml` databases in `autosar/Config/System/`.

There is no CMake wrapper and no CI build in this repository. Details:
`docs/src/content/docs/general/build-system/`.

## Documentation site

The full layered reference (this README's catalogue plus per-module pages and
binary-document summaries) is an **Astro v7 + Starlight** site whose sources
live entirely in [`docs/`](docs/):

```sh
cd docs
npm install      # install Astro 7 + Starlight (pinned in docs/package.json)
npm run dev      # local preview with hot reload
npm run build    # static output in docs/dist/
npm run preview  # serve the built output
```

`docs/astro.config.mjs` derives the GitHub Pages `site`/`base` from the
`GITHUB_REPOSITORY` environment variable (with `SITE_URL`/`SITE_BASE`
overrides), so forks deploy without editing any config — no owner or
repository name is hardcoded anywhere in the site sources.

## Ford T3T6 platform

The Ford T3T6 platform underpins vehicles such as the Ford Transit Custom,
Tourneo Custom, Ranger, Everest, Explorer, Territory and Transit Connect.

## Contributing

Contributions are welcome via pull requests. Please respect module ownership:
hand-edit only **Custom** modules and integration configuration — never
Vector/Renesas deliveries (change their DaVinci/ECUC configuration instead)
— and keep the docs site in sync for any module you touch.

## License

This project is licensed under the **MIT License** — see [LICENSE](LICENSE).
The MIT licence covers project-owned content; third-party deliveries (Vector
MICROSAR, Renesas MCAL, Green Hills toolchain, bundled runtimes) remain under
their own vendor licence terms — see the appendix in [LICENSE](LICENSE).
