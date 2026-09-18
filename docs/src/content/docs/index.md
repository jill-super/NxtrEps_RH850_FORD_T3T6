---
title: "EPS AUTOSAR documentation"
description: "Electric Power Steering (Ford T3T6, Renesas RH850) AUTOSAR documentation: layers, modules, origin and converted design docs."
---

import { Card, CardGrid } from '@astrojs/starlight/components';

# Electric Power Steering — AUTOSAR documentation

Complete reference for the Ford T3T6 Electric Power Steering ECU software:
AUTOSAR-layered C code for the Renesas RH850, built with the Green Hills
MULTI toolchain and the Vector MICROSAR (DaVinci/SIP) stack.

<CardGrid stagger>
  <Card title="Application Software" icon="puzzle">
    Steering features, Ford customer functions, CAN gateways and platform
    libraries. See [ASW](./asw/).
  </Card>
  <Card title="Complex Device Drivers" icon="cpu">
    MCU/peripheral configuration and EPS sensing/power services with direct
    hardware access. See [CDD](./cdd/).
  </Card>
  <Card title="Basic Software" icon="layers">
    Vector MICROSAR communication, memory, diagnostics, OS and RTE. See
    [BSW](./bsw/).
  </Card>
  <Card title="MCAL" icon="chip">
    Renesas P1x-C/X1x drivers: Mcu, Port, Dio, Spi, Fls, Wdg. See
    [MCAL](./mcal/).
  </Card>
  <Card title="Tools" icon="wrench">
    Host utilities: compilers, generators, checkers. See [Tools](./tools/).
  </Card>
  <Card title="Integration" icon="setting">
    Top-level ECU build: generated code, GHS projects, CAN databases. See
    [Integration](./integration/).
  </Card>
</CardGrid>

## Vector vs custom

Every module page carries an origin badge:

- **Vector-provided · MICROSAR** — third-party BSW from the Vector SIP delivery,
  configured with DaVinci/ECUC and **not** hand-edited.
- **Vector-provided · customised** — Vector template with project-specific
  mapping (only `IoHwAb`).
- **Renesas-provided · MCAL** — Renesas P1x-C/X1x driver delivery.
- **Custom · Nexteer in-house** — project-owned SW-Cs, complex drivers and
  services (RTE/generator file headers may still mention Vector — that is the
  *generator*, not the owner).
- **Host tool / Integration** — build-time tooling or aggregated configuration.

How this is decided is documented in [Vector vs custom](./general/origin-guide/),
including the copyright-header methodology and its limits.

## Binary design documents

`doc/` folders across the repo ship Word/PDF originals (integration manuals,
MDDs, Vector Technical References, review checklists). They are inventoried in
[Document inventory](./general/document-inventory/) and each module page links
to Markdown summaries of its own documents. Binary originals cannot be rendered
by this site, so each summary states its source file, size, expected coverage
(from filename and module context) and where the original lives in the repo.

## Reading order

1. [Architecture](./general/architecture/) — ECU, layers, safety and comms.
2. [Build system](./general/build-system/) — how the image is produced.
3. Layer indexes ([ASW](./asw/), [CDD](./cdd/), [BSW](./bsw/), [MCAL](./mcal/))
   and then individual module pages.
