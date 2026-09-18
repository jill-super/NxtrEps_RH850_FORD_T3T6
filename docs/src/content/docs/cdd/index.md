---
title: "Complex Device Drivers (CDD)"
description: "Project-specific complex drivers and ECU services with direct hardware access: MCU/peripheral configuration and diagnostics (CM*) and EPS sensing, power and motor-control services (ES*)."
---


# Complex Device Drivers (CDD)

Project-specific complex drivers and ECU services with direct hardware access: MCU/peripheral configuration and diagnostics (CM*) and EPS sensing, power and motor-control services (ES*).

Modules in this layer: **54**.

| Component | Repo directory | Origin | Docs |
| --- | --- | --- | --- |
| [Exception Handling (CM101B)](./cm101b-excpnhndlg-impl/) | `CM101B_ExcpnHndlg_Impl/` | Custom · Nexteer in-house | 2 |
| [Flash Memory (CM102B)](./cm102b-flsmem-impl/) | `CM102B_FlsMem_Impl/` | Custom · Nexteer in-house | 2 |
| [RAM memory (CM103B)](./cm103b-rammem-impl/) | `CM103B_RamMem_Impl/` | Custom · Nexteer in-house | 2 |
| [ECM Output and Diagnostics (CM104B)](./cm104b-ecmoutpanddiagc-impl/) | `CM104B_EcmOutpAndDiagc_Impl/` | Custom · Nexteer in-house | 2 |
| [MCU Core Configuration and Diagnostics (CM106B)](./cm106b-mcucorecfganddiagc-impl/) | `CM106B_McuCoreCfgAndDiagc_Impl/` | Custom · Nexteer in-house | 2 |
| [Guard Configuration and Diagnostics (CM107B)](./cm107b-guardcfganddiagc-impl/) | `CM107B_GuardCfgAndDiagc_Impl/` | Custom · Nexteer in-house | 2 |
| [Clock Configuration and Monitor (CM109B)](./cm109b-clkcfgandmon-impl/) | `CM109B_ClkCfgAndMon_Impl/` | Custom · Nexteer in-house | 2 |
| [Critical register verification (CM111A)](./cm111a-vrfycritreg-impl/) | `CM111A_VrfyCritReg_Impl/` | Custom · Nexteer in-house | 2 |
| [Core Voltage Monitor (CM112B)](./cm112b-corevltgmonr-impl/) | `CM112B_CoreVltgMonr_Impl/` | Custom · Nexteer in-house | 2 |
| [DMA Configuration and Use (CM201A)](./cm201a-dmacfganduse-impl/) | `CM201A_DmaCfgAndUse_Impl/` | Custom · Nexteer in-house | 2 |
| [ADCF 0 Configuration and Use (CM301A)](./cm301a-adcf0cfganduse-impl/) | `CM301A_Adcf0CfgAndUse_Impl/` | Custom · Nexteer in-house | 2 |
| [ADCF 1 Configuration and Use (CM321A)](./cm321a-adcf1cfganduse-impl/) | `CM321A_Adcf1CfgAndUse_Impl/` | Custom · Nexteer in-house | 2 |
| [Handwheel Torque 1 Measurement (CM660A)](./cm660a-hwtq1meas-impl/) | `CM660A_HwTq1Meas_Impl/` | Custom · Nexteer in-house | 2 |
| [Handwheel Angle 1 Measurement (CM670A)](./cm670a-hwag1meas-impl/) | `CM670A_HwAg1Meas_Impl/` | Custom · Nexteer in-house | 2 |
| [Handwheel Torque 8 Measurement (CM690D)](./cm690d-hwtq8meas-impl/) | `CM690D_HwTq8Meas_Impl/` | Custom · Nexteer in-house | 2 |
| [UART 0 Configuration and Use (CM760A)](./cm760a-uart0cfganduse-impl/) | `CM760A_Uart0CfgAndUse_Impl/` | Custom · Nexteer in-house | 2 |
| [UART 1 Configuration and Use (CM765A)](./cm765a-uart1cfganduse-impl/) | `CM765A_Uart1CfgAndUse_Impl/` | Custom · Nexteer in-house | 2 |
| [GTM Configuration and Use (CM770A)](./cm770a-gtmcfganduse-impl/) | `CM770A_GtmCfgAndUse_Impl/` | Custom · Nexteer in-house | 2 |
| [Sync CRC (CM800A)](./cm800a-synccrc-impl/) | `CM800A_SyncCrc_Impl/` | Custom · Nexteer in-house | 2 |
| [MCU Diagnostics (ES002A)](./es002a-mcudiagc-impl/) | `ES002A_McuDiagc_Impl/` | Custom · Nexteer in-house | 2 |
| [Power Disconnect (ES003C)](./es003c-pwrdiscnct-impl/) | `ES003C_PwrDiscnct_Impl/` | Custom · Nexteer in-house | 2 |
| [Power Up Sequence (ES004A)](./es004a-pwrupseq-impl/) | `ES004A_PwrUpSeq_Impl/` | Custom · Nexteer in-house | 2 |
| [Tmpl monitor (ES005C)](./es005c-tmplmonr-impl/) | `ES005C_TmplMonr_Impl/` | Custom · Nexteer in-house | 2 |
| [NVRAM proxy service (ES006A)](./es006a-nvm-impl/) | `ES006A_NvM_Impl/` | Custom · Nexteer in-house | 1 |
| [Power Supply (ES008A)](./es008a-pwrsply-impl/) | `ES008A_PwrSply_Impl/` | Custom · Nexteer in-house | 2 |
| [Dual ECU Identification (ES011A)](./es011a-dualecuidn-impl/) | `ES011A_DualEcuIdn_Impl/` | Custom · Nexteer in-house | 2 |
| [System State Mode (ES100A)](./es100a-sysstmod-impl/) | `ES100A_SysStMod_Impl/` | Custom · Nexteer in-house | 2 |
| [Diagnostics Manager (ES101A)](./es101a-diagcmgr-impl/) | `ES101A_DiagcMgr_Impl/` | Custom · Nexteer in-house | 3 |
| [Polarity Configuration (ES102A)](./es102a-polaritycfg-impl/) | `ES102A_PolarityCfg_Impl/` | Custom · Nexteer in-house | 2 |
| [XCP Interface (ES104A)](./es104a-xcpif-impl/) | `ES104A_XcpIf_Impl/` | Custom · Nexteer in-house | 2 |
| [Shutdown Mechanism (ES108A)](./es108a-shtdwnmech-impl/) | `ES108A_ShtdwnMech_Impl/` | Custom · Nexteer in-house | 2 |
| [Current Measurement (ES200B)](./es200b-currmeas-impl/) | `ES200B_CurrMeas_Impl/` | Custom · Nexteer in-house | 2 |
| [Current Measurement Arbitration (ES208A)](./es208a-currmeasarbn-impl/) | `ES208A_CurrMeasArbn_Impl/` | Custom · Nexteer in-house | 2 |
| [Current Measurement Correlation (ES209B)](./es209b-currmeascorrln-impl/) | `ES209B_CurrMeasCorrln_Impl/` | Custom · Nexteer in-house | 2 |
| [ECU Temperature Measurement (ES210A)](./es210a-ecutmeas-impl/) | `ES210A_EcuTMeas_Impl/` | Custom · Nexteer in-house | 2 |
| [Handwheel Torque 9 Measurement (ES224A)](./es224a-hwtq9meas-impl/) | `ES224A_HwTq9Meas_Impl/` | Custom · Nexteer in-house | 2 |
| [Handwheel Torque 10 Measurement (ES225A)](./es225a-hwtq10meas-impl/) | `ES225A_HwTq10Meas_Impl/` | Custom · Nexteer in-house | 2 |
| [Handwheel Torque Arbitration (ES228C)](./es228c-hwtqarbn-impl/) | `ES228C_HwTqArbn_Impl/` | Custom · Nexteer in-house | 2 |
| [Handwheel Torque Correlation (ES229C)](./es229c-hwtqcorrln-impl/) | `ES229C_HwTqCorrln_Impl/` | Custom · Nexteer in-house | 2 |
| [Handwheel Angle Arbitration (ES238B)](./es238b-hwagarbn-impl/) | `ES238B_HwAgArbn_Impl/` | Custom · Nexteer in-house | 2 |
| [Handwheel Angle Correlation (ES239B)](./es239b-hwagcorrln-impl/) | `ES239B_HwAgCorrln_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Angle 2 Measurement (ES241A)](./es241a-motag2meas-impl/) | `ES241A_MotAg2Meas_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Angle 5 Measurement (ES242A)](./es242a-motag5meas-impl/) | `ES242A_MotAg5Meas_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Angle 6 Measurement (ES243A)](./es243a-motag6meas-impl/) | `ES243A_MotAg6Meas_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Angle Compensation (ES247A)](./es247a-motagcmp-impl/) | `ES247A_MotAgCmp_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Angle Arbitration (ES248A)](./es248a-motagarbn-impl/) | `ES248A_MotAgArbn_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Angle Correlation (ES249A)](./es249a-motagcorrln-impl/) | `ES249A_MotAgCorrln_Impl/` | Custom · Nexteer in-house | 2 |
| [Battery Voltage (ES250B)](./es250b-battvltg-impl/) | `ES250B_BattVltg_Impl/` | Custom · Nexteer in-house | 2 |
| [Battery Voltage Correlation (ES259B)](./es259b-battvltgcorrln-impl/) | `ES259B_BattVltgCorrln_Impl/` | Custom · Nexteer in-house | 2 |
| [Motor Angle Software Calibration (ES280A)](./es280a-motagswcal-impl/) | `ES280A_MotAgSwCal_Impl/` | Custom · Nexteer in-house | 2 |
| [Sine Voltage Generation (ES300A)](./es300a-sinvltggenn-impl/) | `ES300A_SinVltgGenn_Impl/` | Custom · Nexteer in-house | 2 |
| [Gate Driver 0 Control (ES311A)](./es311a-gatedrv0ctrl-impl/) | `ES311A_GateDrv0Ctrl_Impl/` | Custom · Nexteer in-house | 2 |
| [Tuning Selection Management (ES400A)](./es400a-tunselnmngt-impl/) | `ES400A_TunSelnMngt_Impl/` | Custom · Nexteer in-house | 2 |
| [Electrical global parameters (ES999A)](./es999a-elecglbprm-impl/) | `ES999A_ElecGlbPrm_Impl/` | Custom · Nexteer in-house | 1 |

:::note[Slug convention]
Page slugs are lowercased with non-alphanumerics replaced by hyphens (e.g. `SF001A_Assi_Impl` → `sf001a-assi-impl`). The repo directory name is always shown so pages trace back to the code. :::
