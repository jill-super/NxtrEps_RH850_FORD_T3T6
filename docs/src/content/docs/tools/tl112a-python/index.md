---
title: "Python host environment (TL112A)"
description: "TL112A_Python: Bundled Python 2.7 runtime plus project libraries used by generators and checks."
---


import { Badge } from '@astrojs/starlight/components';

# Python host environment (TL112A)

Repo directory: `TL112A_Python/` · Layer: `tools`

<Badge text="Host tool · third-party" variant="default" />

## Purpose and responsibility

Bundled Python 2.7 runtime plus project libraries used by generators and checks.

## Origin

**Host tool · third-party.** Host-side tooling (Python Software Foundation (bundled 2.7 runtime)); no target ECU code.

:::note[Build-time artefact]
Not target ECU functionality: tooling or aggregated integration data. :::

## Key files

- `include/` (42 entries): `ZipLib.py`, `checksumdir`, `checksumdir.zip`, `csscompressor`, `csscompressor.zip`, `dateutil`, `dateutil.zip`, `jsmin`, `jsmin.zip`, `mako`, `mako.zip`, `markdown`, `markdown.zip`, `numpy` (+28 more)
- `tools/` (16 entries): `DLLs`, `Lib`, `Microsoft.VC90.CRT.manifest`, `msvcm90.dll`, `msvcp90.dll`, `msvcr90.dll`, `pylint.exe`, `python.exe`, `python27.dll`, `pythoncom27.dll`, `pythoncomloader27.dll`, `pythonw.exe`, `pywintypes27.dll`, `qt.conf` (+2 more)
- `doc/` (4 entries): `AddingNewLibraries.txt`, `TL112A_Python Peer Review Checklist.xlsm`, `pylint`, `python2710.chm`

## Generated code and configuration

- No generator/contract folders observed.

## Public API

No runtime public API (tooling/integration data).

## Usage example

N/A — see the integration and build-system pages for how this artefact is used.

## Dependencies

- See the build-system and integration pages.

## Converted documentation

- [AddingNewLibraries.txt](./addingnewlibraries/)

## Repository location

Repo path: `TL112A_Python/` — subfolders present: `include/`, `doc/`, `tools/`.
