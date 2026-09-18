---
title: "Application Software (ASW)"
description: "RTE software components (SW-Cs) and shared platform libraries: steering features (SF*), Ford customer features (CF*), CAN message gateways (MM*), manufacturing/service (NM*), test hooks (DF*), and Nexteer platform librar"
---


# Application Software (ASW)

RTE software components (SW-Cs) and shared platform libraries: steering features (SF*), Ford customer features (CF*), CAN message gateways (MM*), manufacturing/service (NM*), test hooks (DF*), and Nexteer platform libraries (AR*).

Modules in this layer: **105**.

| Component | Repo directory | Origin | Docs |
| --- | --- | --- | --- |
| [Nexteer Math Library (AR100A)](./ar100a-nxtrmath-impl/) | `AR100A_NxtrMath_Impl/` | Custom · Nexteer in-house | 2 |
| [Nexteer Interpolation (AR101A)](./ar101a-nxtrintrpn-impl/) | `AR101A_NxtrIntrpn_Impl/` | Custom · Nexteer in-house | 1 |
| [Nexteer Time (AR102B)](./ar102b-nxtrti-impl/) | `AR102B_NxtrTi_Impl/` | Custom · Nexteer in-house | 1 |
| [Nexteer Fixed Point (AR103A)](./ar103a-nxtrfixdpt-impl/) | `AR103A_NxtrFixdPt_Impl/` | Custom · Nexteer in-house | 1 |
| [Nexteer Filter (AR104A)](./ar104a-nxtrfil-impl/) | `AR104A_NxtrFil_Impl/` | Custom · Nexteer in-house | 1 |
| [AUTOSAR support types (AR200A)](./ar200a-arsuprt-impl/) | `AR200A_ArSuprt_Impl/` | Custom · Nexteer in-house | 0 |
| [Compiler support types (AR201A)](./ar201a-arcplrsuprt-impl/) | `AR201A_ArCplrSuprt_Impl/` | Custom · Nexteer in-house | 0 |
| [Microcontroller support library (AR202A)](./ar202a-microctrlrsuprt-impl/) | `AR202A_MicroCtrlrSuprt_Impl/` | Custom · Nexteer in-house | 3 |
| [Motor Control Manager (AR300A)](./ar300a-motctrlmgr-impl/) | `AR300A_MotCtrlMgr_Impl/` | Custom · Nexteer in-house | 3 |
| [Inter-Micro Communication Arbitration (AR350A)](./ar350a-imcarbn-impl/) | `AR350A_ImcArbn_Impl/` | Custom · Nexteer in-house | 2 |
| [Nexteer Startup (AR400A)](./ar400a-nxtrstrtup-impl/) | `AR400A_NxtrStrtUp_Impl/` | Custom · Nexteer in-house | 1 |
| [Nexteer Development Error Tracer (AR998A)](./ar998a-nxtrdet-impl/) | `AR998A_NxtrDet_Impl/` | Custom · Nexteer in-house | 3 |
| [Architecture global parameters (AR999A)](./ar999a-archglbprm-impl/) | `AR999A_ArchGlbPrm_Impl/` | Custom · Nexteer in-house | 0 |
| [Ford System State (CF052A)](./cf052a-fordsysst-impl/) | `CF052A_FordSysSt_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Command Arbitration (CF065A)](./cf065a-fordcmdarbn-impl/) | `CF065A_FordCmdArbn_Impl/` | Custom · Nexteer in-house | 0 |
| [Ford Handwheel Torque Command Overall Limiter (CF067A)](./cf067a-fordhwtqcmdovrllimr-impl/) | `CF067A_FordHwTqCmdOvrlLimr_Impl/` | Custom · Nexteer in-house | 1 |
| [Ford Handwheel Torque Coding (CF076A)](./cf076a-fordhwtqcdng-impl/) | `CF076A_FordHwTqCdng_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Black Box Interface Common (CF110A)](./cf110a-fordblaboxifcmn-impl/) | `CF110A_FordBlaBoxIfCmn_Impl/` | Custom · Nexteer in-house | 0 |
| [Ford Black Box Interface Component 1 (CF111A)](./cf111a-fordblaboxifcmp1-impl/) | `CF111A_FordBlaBoxIfCmp1_Impl/` | Custom · Nexteer in-house | 0 |
| [Ford Black Box Interface Component 2 (CF112A)](./cf112a-fordblaboxifcmp2-impl/) | `CF112A_FordBlaBoxIfCmp2_Impl/` | Custom · Nexteer in-house | 0 |
| [Fault Injection (DF001A)](./df001a-fltinj-impl/) | `DF001A_FltInj_Impl/` | Custom · Nexteer in-house | 2 |
| [Swp test support (DF002A)](./df002a-swp-impl/) | `DF002A_Swp_Impl/` | Custom · Nexteer in-house | 2 |
| [Checkpoint monitor (Ford001A)](./ford001a-chkpt-impl/) | `Ford001A_ChkPt_Impl/` | Custom · Nexteer in-house | 0 |
| [Ford Message 07D — High-Speed Bus (MM052A)](./mm052a-fordmsg07dbushispd-impl/) | `MM052A_FordMsg07DBusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 083 — High-Speed Bus (MM054A)](./mm054a-fordmsg083bushispd-impl/) | `MM054A_FordMsg083BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 091 — High-Speed Bus (MM056A)](./mm056a-fordmsg091bushispd-impl/) | `MM056A_FordMsg091BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 215 — High-Speed Bus (MM057A)](./mm057a-fordmsg215bushispd-impl/) | `MM057A_FordMsg215BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 167 — High-Speed Bus (MM059A)](./mm059a-fordmsg167bushispd-impl/) | `MM059A_FordMsg167BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 202 — High-Speed Bus (MM061A)](./mm061a-fordmsg202bushispd-impl/) | `MM061A_FordMsg202BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 213 — High-Speed Bus (MM063A)](./mm063a-fordmsg213bushispd-impl/) | `MM063A_FordMsg213BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 216 — High-Speed Bus (MM064A)](./mm064a-fordmsg216bushispd-impl/) | `MM064A_FordMsg216BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 217 — High-Speed Bus (MM065A)](./mm065a-fordmsg217bushispd-impl/) | `MM065A_FordMsg217BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 230 — High-Speed Bus (MM066A)](./mm066a-fordmsg230bushispd-impl/) | `MM066A_FordMsg230BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 414 — High-Speed Bus (MM070A)](./mm070a-fordmsg414bushispd-impl/) | `MM070A_FordMsg414BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 3B3 — High-Speed Bus (MM072A)](./mm072a-fordmsg3b3bushispd-impl/) | `MM072A_FordMsg3B3BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 3CA — High-Speed Bus (MM073A)](./mm073a-fordmsg3cabushispd-impl/) | `MM073A_FordMsg3CABusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 3D3 — High-Speed Bus (MM074A)](./mm074a-fordmsg3d3bushispd-impl/) | `MM074A_FordMsg3D3BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 3D7 — High-Speed Bus (MM075A)](./mm075a-fordmsg3d7bushispd-impl/) | `MM075A_FordMsg3D7BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 40A — High-Speed Bus (MM076A)](./mm076a-fordmsg40abushispd-impl/) | `MM076A_FordMsg40ABusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 415 — High-Speed Bus (MM077A)](./mm077a-fordmsg415bushispd-impl/) | `MM077A_FordMsg415BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 41A — High-Speed Bus (MM078A)](./mm078a-fordmsg41abushispd-impl/) | `MM078A_FordMsg41ABusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 41E — High-Speed Bus (MM079A)](./mm079a-fordmsg41ebushispd-impl/) | `MM079A_FordMsg41EBusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 430 — High-Speed Bus (MM081A)](./mm081a-fordmsg430bushispd-impl/) | `MM081A_FordMsg430BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 443 — High-Speed Bus (MM086A)](./mm086a-fordmsg443bushispd-impl/) | `MM086A_FordMsg443BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 4B0 — High-Speed Bus (MM089A)](./mm089a-fordmsg4b0bushispd-impl/) | `MM089A_FordMsg4B0BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 459 — High-Speed Bus (MM090A)](./mm090a-fordmsg459bushispd-impl/) | `MM090A_FordMsg459BusHiSpd_Impl/` | Custom · Nexteer in-house | 0 |
| [Ford Message 47A — High-Speed Bus (MM092A)](./mm092a-fordmsg47abushispd-impl/) | `MM092A_FordMsg47ABusHiSpd_Impl/` | Custom · Nexteer in-house | 0 |
| [Ford Message 077 — High-Speed Bus (MM124A)](./mm124a-fordmsg077bushispd-impl/) | `MM124A_FordMsg077BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 2FD — High-Speed Bus (MM134A)](./mm134a-fordmsg2fdbushispd-impl/) | `MM134A_FordMsg2FDBusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 417 — High-Speed Bus (MM518A)](./mm518a-fordmsg417bushispd-impl/) | `MM518A_FordMsg417BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 5B5 — High-Speed Bus (MM519A)](./mm519a-fordmsg5b5bushispd-impl/) | `MM519A_FordMsg5B5BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 07E — High-Speed Bus (MM531A)](./mm531a-fordmsg07ebushispd-impl/) | `MM531A_FordMsg07EBusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 082 — High-Speed Bus (MM532A)](./mm532a-fordmsg082bushispd-impl/) | `MM532A_FordMsg082BusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Ford Message 3CC — High-Speed Bus (MM533A)](./mm533a-fordmsg3ccbushispd-impl/) | `MM533A_FordMsg3CCBusHiSpd_Impl/` | Custom · Nexteer in-house | 2 |
| [Common Manufacturing Service (NM001A)](./nm001a-cmnmfgsrv-impl/) | `NM001A_CmnMfgSrv_Impl/` | Custom · Nexteer in-house | 4 |
| [Nexteer Software IDs (NM003A)](./nm003a-nxtrswids-impl/) | `NM003A_NxtrSwIds_Impl/` | Custom · Nexteer in-house | 0 |
| [Nexteer Calibration IDs (NM004A)](./nm004a-nxtrcalids-impl/) | `NM004A_NxtrCalIds_Impl/` | Custom · Nexteer in-house | 0 |
| [Motor Velocity Control (NM100A)](./nm100a-motvelctrl-impl/) | `NM100A_MotVelCtrl_Impl/` | Custom · Nexteer in-house | 2 |
| [Assist (SF001A)](./sf001a-assi-impl/) | `SF001A_Assi_Impl/` | Custom · Nexteer in-house | 2 |
| [Return (SF002A)](./sf002a-rtn-impl/) | `SF002A_Rtn_Impl/` | Custom · Nexteer in-house | 2 |
| [Damping (SF003A)](./sf003a-dampg-impl/) | `SF003A_Dampg_Impl/` | Custom · Nexteer in-house | 2 |
| [Assist Sum Limit (SF004B)](./sf004b-assisumlim-impl/) | `SF004B_AssiSumLim_Impl/` | Custom · Nexteer in-house | 2 |
| [Steering Output Control (SF005A)](./sf005a-stoutpctrl-impl/) | `SF005A_StOutpCtrl_Impl/` | Custom · Nexteer in-house | 2 |
| [Torque Estimation (SF006A)](./sf006a-testimn-impl/) | `SF006A_TEstimn_Impl/` | Custom · Nexteer in-house | 2 |
| [System Friction Learning (SF007A)](./sf007a-sysfriclrng-impl/) | `SF007A_SysFricLrng_Impl/` | Custom · Nexteer in-house | 2 |
| [Duty Cycle Thermal Protection (SF009A)](./sf009a-dutycycthermprotn-impl/) | `SF009A_DutyCycThermProtn_Impl/` | Custom · Nexteer in-house | 2 |
| [End of Travel Learning (SF011A)](./sf011a-eotlrng-impl/) | `SF011A_EotLrng_Impl/` | Custom · Nexteer in-house | 2 |
| [Hysteresis Compensation (SF012A)](./sf012a-hyscmp-impl/) | `SF012A_HysCmp_Impl/` | Custom · Nexteer in-house | 2 |
| [Inertia Compensation Velocity (SF014A)](./sf014a-inertiacmpvel-impl/) | `SF014A_InertiaCmpVel_Impl/` | Custom · Nexteer in-house | 2 |
| [Vehicle Speed Limiter (SF016A)](./sf016a-vehspdlimr-impl/) | `SF016A_VehSpdLimr_Impl/` | Custom · Nexteer in-house | 2 |
| [High Load Stall Limiter (SF017A)](./sf017a-hiloadstalllimr-impl/) | `SF017A_HiLoadStallLimr_Impl/` | Custom · Nexteer in-house | 2 |
| [End of Travel Protection (SF018A)](./sf018a-eotprotn-impl/) | `SF018A_EotProtn_Impl/` | Custom · Nexteer in-house | 2 |
| [Power Limiter (SF019B)](./sf019b-pwrlimr-impl/) | `SF019B_PwrLimr_Impl/` | Custom · Nexteer in-house | 2 |
| [Position Tracking Servo (SF020B)](./sf020b-posntrakgservo-impl/) | `SF020B_PosnTrakgServo_Impl/` | Custom · Nexteer in-house | 2 |
| [Tuning Selection Authority (SF023A)](./sf023a-tunselnauthy-impl/) | `SF023A_TunSelnAuthy_Impl/` | Custom · Nexteer in-house | 2 |
| [End of Travel Protection Firewall (SF027A)](./sf027a-eotprotnfwl-impl/) | `SF027A_EotProtnFwl_Impl/` | Custom · Nexteer in-house | 2 |
| [Assist High Frequency (SF028A)](./sf028a-assihifrq-impl/) | `SF028A_AssiHiFrq_Impl/` | Custom · Nexteer in-house | 2 |
| [Stability Compensation (SF029A)](./sf029a-stabycmp-impl/) | `SF029A_StabyCmp_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Torque Command Scaling (SF032A)](./sf032a-mottqcmdsca-impl/) | `SF032A_MotTqCmdSca_Impl/` | Custom · Nexteer in-house | 2 |
| [Vehicle Signal Coding (SF033A)](./sf033a-vehsigcdng-impl/) | `SF033A_VehSigCdng_Impl/` | Custom · Nexteer in-house | 2 |
| [Assist Path Sum (SF034B)](./sf034b-assipahsum-impl/) | `SF034B_AssiPahSum_Impl/` | Custom · Nexteer in-house | 2 |
| [Damping Path Sum (SF035B)](./sf035b-dampgpahsum-impl/) | `SF035B_DampgPahSum_Impl/` | Custom · Nexteer in-house | 2 |
| [Return Path Firewall (SF036A)](./sf036a-rtnpahfwl-impl/) | `SF036A_RtnPahFwl_Impl/` | Custom · Nexteer in-house | 2 |
| [Limiter Coding (SF038A)](./sf038a-limrcdng-impl/) | `SF038A_LimrCdng_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Velocity (SF040A)](./sf040a-motvel-impl/) | `SF040A_MotVel_Impl/` | Custom · Nexteer in-house | 2 |
| [Compliance Error (SF041A)](./sf041a-cmplncerr-impl/) | `SF041A_CmplncErr_Impl/` | Custom · Nexteer in-house | 2 |
| [Handwheel Angle Sensorless (SF042A)](./sf042a-hwagsnsrls-impl/) | `SF042A_HwAgSnsrls_Impl/` | Custom · Nexteer in-house | 2 |
| [Handwheel Angle System Arbitration (SF045A)](./sf045a-hwagsysarbn-impl/) | `SF045A_HwAgSysArbn_Impl/` | Custom · Nexteer in-house | 2 |
| [Torque Loss of Assist (SF048A)](./sf048a-tqloa-impl/) | `SF048A_TqLoa_Impl/` | Custom · Nexteer in-house | 2 |
| [Loss of Assist Manager (SF049B)](./sf049b-loamgr-impl/) | `SF049B_LoaMgr_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Torque Transitional Damping (SF050A)](./sf050a-mottqtranldampg-impl/) | `SF050A_MotTqTranlDampg_Impl/` | Custom · Nexteer in-house | 2 |
| [Driver Torque Estimation (SF056A)](./sf056a-drvrtqestimn-impl/) | `SF056A_DrvrTqEstimn_Impl/` | Custom · Nexteer in-house | 2 |
| [System Performance Status (SF059A)](./sf059a-sysprfmncsts-impl/) | `SF059A_SysPrfmncSts_Impl/` | Custom · Nexteer in-house | 2 |
| [Dual Controller Output Manager (SF062B)](./sf062b-dualctrlroutpmgr-impl/) | `SF062B_DualCtrlrOutpMgr_Impl/` | Custom · Nexteer in-house | 2 |
| [Inter-Micro Communication Signal Arbitration (SF063A)](./sf063a-imcsigarbn-impl/) | `SF063A_ImcSigArbn_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Quadrant Detection (SF101A)](./sf101a-motquaddetn-impl/) | `SF101A_MotQuadDetn_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Control Parameters Estimation (SF102A)](./sf102a-motctrlprmestimn-impl/) | `SF102A_MotCtrlPrmEstimn_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Reference Model (SF103A)](./sf103a-motrefmdl-impl/) | `SF103A_MotRefMdl_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Current Regulator Configuration (SF104A)](./sf104a-motcurrregcfg-impl/) | `SF104A_MotCurrRegCfg_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Current Regulator Voltage Limiter (SF105A)](./sf105a-motcurrregvltglimr-impl/) | `SF105A_MotCurrRegVltgLimr_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Ripple Cogging Configuration (SF106A)](./sf106a-motrplcoggcfg-impl/) | `SF106A_MotRplCoggCfg_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Ripple Cogging Command (SF107A)](./sf107a-motrplcoggcmd-impl/) | `SF107A_MotRplCoggCmd_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Current Peak Estimation (SF108A)](./sf108a-motcurrpeakestimn-impl/) | `SF108A_MotCurrPeakEstimn_Impl/` | Custom · Nexteer in-house | 2 |
| [Electrical Power Consumption (SF109A)](./sf109a-elecpwrcns-impl/) | `SF109A_ElecPwrCns_Impl/` | Custom · Nexteer in-house | 2 |
| [System global parameters (SF999A)](./sf999a-sysglbprm-impl/) | `SF999A_SysGlbPrm_Impl/` | Custom · Nexteer in-house | 0 |

:::note[Slug convention]
Page slugs are lowercased with non-alphanumerics replaced by hyphens (e.g. `SF001A_Assi_Impl` → `sf001a-assi-impl`). The repo directory name is always shown so pages trace back to the code. :::
