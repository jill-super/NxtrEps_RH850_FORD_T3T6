---
title: "Ford T3T6 EPS Implementation (top-level integration)"
description: "_Ford_T3T6_Eps_Impl_A: Top-level ECU integration: generated RTE/BSW code, ECUC/system `.arxml`, GHS projects, linker scripts, stubs and the final link image."
---


import { Badge } from '@astrojs/starlight/components';

# Ford T3T6 EPS Implementation (top-level integration)

Repo directory: `_Ford_T3T6_Eps_Impl_A/` · Layer: `integration`

<Badge text="Integration · project config" variant="default" />

## Purpose and responsibility

Top-level ECU integration: generated RTE/BSW code, ECUC/system `.arxml`, GHS projects, linker scripts, stubs and the final link image.

## Origin

**Integration · project config.** Top-level integration/design container; owns no single driver Licence — aggregates generated and in-house artefacts.

:::note[Build-time artefact]
Not target ECU functionality: tooling or aggregated integration data. :::

## Key files

- `src/` (22 entries): `BswM_Callout_Stubs.c`, `CDD_FordT3T6McuCfg.c`, `CalRegn01Rt01Dummy_Stub.c`, `CalRegn02Rt01ADummy_Stub.c`, `CalRegn02Rt01BDummy_Stub.c`, `Can_Callouts.c`, `CustDiag.c`, `Dcm_Callouts.c`, `DiagSrv.c`, `EcuM_Callout_Stubs.c`, `FordHeader.c`, `IoHwAb_30.c`, `NxtrDet.c`, `Os_Callout_Stubs.c` (+8 more)
- `include/` (27 entries): `Appl_Dem.h`, `Appl_Det.h`, `Appl_Mcu.h`, `BswM_UserTypes.h`, `CDD_FordT3T6McuCfg.h`, `Can_GeneralTypes.h`, `Compiler_Cfg.h`, `CustDiag.h`, `EcuM_UserTypes.h`, `FordHeader.h`, `McuErrInj.h`, `MemMap.h`, `NxtrMcuSuprtLib.h`, `P1X_C_Hardware.h` (+13 more)
- `autosar/` (2 entries): `Config`, `EPS.dpa`
- `generate/` (367 entries): `AR300A_MotCtrlMgr_DataDict.m`, `AR300A_MotCtrlMgr_DataDict.m.tt.log`, `Adcf1CfgAndUse_Cfg.h`, `Appl_Cbk.h`, `BswM_Cfg.h`, `BswM_Lcfg.c`, `BswM_PBcfg.c`, `BswM_Private_Cfg.h`, `BswM_XMI21.xml`, `CDD_Adcf0CfgAndUse_Cfg.h`, `CDD_Adcf0CfgAndUse_Cfg.h.tt.log`, `CDD_ExcpnHndlg_Cfg.h`, `CDD_ExcpnHndlg_Cfg.h.tt.log`, `CDD_FlsMem_Cfg.c` (+353 more)
- `tools/` (17 entries): `CANape`, `CANoe`, `CreateGenerateGHSProject.bat`, `CreateIncludeGHSProject.bat`, `CreateScriptsGHSProject.bat`, `CreateSrcGHSProject.bat`, `DataDict`, `DatabaseFiles`, `LaunchProject.bat`, `SIP`, `T3T6.gpj`, `dr7f701373.dvf`, `dr7f701373.ld`, `generate.gpj` (+3 more)
- `doc/` (4 entries): `BootloaderCompatibility.ini`, `Component Integration Review Checklist.xlsm`, `ProjectTraits.ini`, `log`

## Generated code and configuration

- DaVinci `generate/` output shipped with the module.
- AUTOSAR model fragments: `autosar/` (`.arxml`/`.dpa`/`.dcf`).

## Public API

No runtime public API (tooling/integration data).

## Usage example

N/A — see the integration and build-system pages for how this artefact is used.

## Dependencies

- See the build-system and integration pages.

## Converted documentation

- [DVCfg_AutomationInterfaceDocumentation.pdf](./dvcfg-automationinterfacedocumentation/)
- [AN-ISC-8-1153_ThirdPartyModules.pdf](./an-isc-8-1153-thirdpartymodules/)
- [AN-ISC-8-1170_Use_AR3_SWCs_in_AR4.pdf](./an-isc-8-1170-use-ar3-swcs-in-ar4/)
- [AN-ISC-8-1184_Compiler_Warnings.pdf](./an-isc-8-1184-compiler-warnings/)
- [2558.0_NS_LUA_Nexteer_MSR_Ford_SLP1_RH850-CBD1601056.D00.pdf](./2558-0-ns-lua-nexteer-msr-ford-slp1-rh850-cbd1601056-d00/)
- [IssueReport_CBD1601056.pdf](./issuereport-cbd1601056/)
- [ProductInformation_2_MICROSAR4.pdf](./productinformation-2-microsar4/)
- [ProductInformation_2_MSR_Ford_SLP1.pdf](./productinformation-2-msr-ford-slp1/)
- [Readme_CBD16010056.pdf](./readme-cbd16010056/)
- [ReleaseNotes_3rdPartyMCAL_VectorIntegration.pdf](./releasenotes-3rdpartymcal-vectorintegration/)
- [SafetyManual_CBD1601056_D00.pdf](./safetymanual-cbd1601056-d00/)
- [Startup_Ford_SLP1.pdf](./startup-ford-slp1/)
- [TechnicalReference_3rdParty-MCAL-Integration.pdf](./technicalreference-3rdparty-mcal-integration/)
- [TechnicalReference_Asr_MemoryMapping.pdf](./technicalreference-asr-memorymapping/)
- [TechnicalReference_Cdd.pdf](./technicalreference-cdd/)
- [TechnicalReference_Cdd_Asr4DiagVsg.pdf](./technicalreference-cdd-asr4diagvsg/)
- [TechnicalReference_ComStackLib.pdf](./technicalreference-comstacklib/)
- [TechnicalReference_DaVinciConfigurator_Licenses.pdf](./technicalreference-davinciconfigurator-licenses/)
- [TechnicalReference_DiagA2lGen.pdf](./technicalreference-diaga2lgen/)
- [TechnicalReference_Diag_AsrSwcSecAccess_Ford.pdf](./technicalreference-diag-asrswcsecaccess-ford/)
- [TechnicalReference_ExternalDependenciesOfGenerators.pdf](./technicalreference-externaldependenciesofgenerators/)
- [TechnicalReference_GenTool_CsAsrLegacyDb2SystemDescr_Vector.pdf](./technicalreference-gentool-csasrlegacydb2systemdescr-vector/)
- [TechnicalReference_IdentityManager.pdf](./technicalreference-identitymanager/)
- [TechnicalReference_MSSV.pdf](./technicalreference-mssv/)
- [TechnicalReference_SipModificationChecker.pdf](./technicalreference-sipmodificationchecker/)
- [UserManual_AUTOSAR_Calibration.pdf](./usermanual-autosar-calibration/)
- [DocumentationGuide_VectorAUTOSAR.pdf](./documentationguide-vectorautosar/)
- [CANdelaStudio_Ford_contact.PDF](./candelastudio-ford-contact/)

## Repository location

Repo path: `_Ford_T3T6_Eps_Impl_A/` — subfolders present: `src/`, `include/`, `autosar/`, `doc/`, `tools/`, `generate/`.
