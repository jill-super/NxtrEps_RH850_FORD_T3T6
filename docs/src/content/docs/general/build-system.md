---
title: "Build system"
description: "Compilers, GHS projects, make fragments, DaVinci generation and databooks."
---

# Build system

## Toolchain

- **Compiler:** Green Hills MULTI for RH850/V850, shipped in-tree under `TL120A_Cplr/tools/`
  with IDE/project support in `TL121A_Ide/`.
- **Projects:** Green Hills `.gpj` files — top-level `_Ford_T3T6_Eps_Impl_A/tools/` 
  (`T3T6.gpj`, `src.gpj`, `generate.gpj`, `include.gpj`, `scripts.gpj`) plus per-BSW
  `Can/tools/*.gpj`-style project fragments and `Create*GHSProject.bat` scripts.
- **Make fragments:** each Vector BSW module ships `make/*_{cfg,defs,check,rules}.mak`
  implementing the Vector AUTOSAR makefile interface (included by the global target makefile).

## Generation flow (simplified)

```text
DaVinci/SIP config (TL102A, VectorBswSuprt, autosar/Config/*.arxml)
   -> generate/  (RTE contracts->code, BSW _PBcfg/_Lcfg, MemMap/SchM, A2L)
SW-C DataDict .m databooks (each *_Impl/tools/DataDict + integration merge outputs)
   -> calibration/measurement artefacts (McData/*.a2l)
GHS MULTI build (gpj + make fragments + linker .ld/.dvf)
   -> output/T3T6.elf (+ .rc)
```

- **RTE:** per-SW-C contracts under `tools/contract` and `tools/local/generate`,
  component generation via `TL101A_CptRteGen`, final output in
  `_Ford_T3T6_Eps_Impl_A/generate/`.
- **BSW configuration:** ECUC `.arxml` in `_Ford_T3T6_Eps_Impl_A/autosar/Config/ECUC/`,
  DaVinci update logs under `_Ford_T3T6_Eps_Impl_A/doc/log/`.
- **DataDict:** MATLAB databooks (`tools/DataDict/*.m` per module, merged outputs in
  `_Ford_T3T6_Eps_Impl_A/tools/DataDict/`).
- **Host Python:** `TL112A_Python` bundles the interpreter used by generators/checks.

## Rebuilding

This repo ships its toolchain, so a Windows + GHS environment matching the `.gpj`
projects is the supported path (see the integration `tools/LaunchProject.bat`).
There is no CMake/Ninja wrapper and no CI build configured in this repo
(workflows are intentionally untouched) — see [Preview & publishing](../preview-publishing/)
for the docs site only.
