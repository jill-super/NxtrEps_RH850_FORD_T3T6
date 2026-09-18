---
title: "Basic Software (BSW)"
description: "AUTOSAR Basic Software: Vector MICROSAR communication, memory, system, diagnostics and OS/RTE stacks, plus the ECU-abstraction IoHwAb."
---


# Basic Software (BSW)

AUTOSAR Basic Software: Vector MICROSAR communication, memory, system, diagnostics and OS/RTE stacks, plus the ECU-abstraction IoHwAb.

Modules in this layer: **26**.

| Component | Repo directory | Origin | Docs |
| --- | --- | --- | --- |
| [BSW Mode Manager](./bswm/) | `BswM/` | Vector-provided · MICROSAR | 1 |
| [CAN Driver](./can/) | `Can/` | Vector-provided · MICROSAR | 1 |
| [CAN Interface](./canif/) | `CanIf/` | Vector-provided · MICROSAR | 1 |
| [CAN Network Management](./cannm/) | `CanNm/` | Vector-provided · MICROSAR | 1 |
| [CAN State Manager](./cansm/) | `CanSm/` | Vector-provided · MICROSAR | 1 |
| [CAN Transport Protocol](./cantp/) | `CanTp/` | Vector-provided · MICROSAR | 1 |
| [CAN XCP Transport](./canxcp/) | `CanXcp/` | Vector-provided · MICROSAR | 1 |
| [Communication](./com/) | `Com/` | Vector-provided · MICROSAR | 1 |
| [Communication Manager](./comm/) | `ComM/` | Vector-provided · MICROSAR | 1 |
| [CRC Library](./crc/) | `Crc/` | Vector-provided · MICROSAR | 1 |
| [Diagnostic Communication Manager](./dcm/) | `Dcm/` | Vector-provided · MICROSAR | 1 |
| [Diagnostic Event Manager](./dem/) | `Dem/` | Vector-provided · MICROSAR | 1 |
| [Development Error Tracer](./det/) | `Det/` | Vector-provided · MICROSAR | 1 |
| [ECU Configuration](./ecuc/) | `EcuC/` | Vector-provided · MICROSAR | 1 |
| [ECU State Manager](./ecum/) | `EcuM/` | Vector-provided · MICROSAR | 1 |
| [Flash EEPROM Emulation (Small Sector)](./fee-30-smallsector/) | `Fee_30_SmallSector/` | Vector-provided · MICROSAR | 1 |
| [I/O Hardware Abstraction](./iohwab/) | `IoHwAb/` | Vector-provided · customised | 1 |
| [Memory Abstraction Interface](./memif/) | `MemIf/` | Vector-provided · MICROSAR | 1 |
| [Network Management](./nm/) | `Nm/` | Vector-provided · MICROSAR | 1 |
| [NVRAM Manager](./nvm/) | `NvM/` | Vector-provided · MICROSAR | 1 |
| [Operating System](./os/) | `Os/` | Vector-provided · MICROSAR | 2 |
| [PDU Router](./pdur/) | `PduR/` | Vector-provided · MICROSAR | 1 |
| [Run-Time Environment](./rte/) | `Rte/` | Vector-provided · MICROSAR | 3 |
| [Watchdog Interface](./wdgif/) | `WdgIf/` | Vector-provided · MICROSAR | 1 |
| [Watchdog Manager](./wdgm/) | `WdgM/` | Vector-provided · MICROSAR | 1 |
| [Universal Measurement and Calibration Protocol](./xcp/) | `Xcp/` | Vector-provided · MICROSAR | 4 |

:::note[Slug convention]
Page slugs are lowercased with non-alphanumerics replaced by hyphens (e.g. `SF001A_Assi_Impl` → `sf001a-assi-impl`). The repo directory name is always shown so pages trace back to the code. :::
