---
title: "Vector vs custom"
description: "How module origin is determined and what each badge means."
---

# Vector vs custom

## Badges

| Badge | Meaning | Examples |
| --- | --- | --- |
| Vector-provided · MICROSAR | Vector SIP delivery, DaVinci-configured, do not hand-edit | `Can`, `Com`, `Os`, `NvM`, `Dcm` |
| Vector-provided · customised | Vector template + project mapping | `IoHwAb` (mapping in integration `src/IoHwAb_30.c`) |
| Renesas-provided · MCAL | Renesas P1x-C/X1x driver delivery | `Mcu`, `Port`, `Dio`, `Spi`, `Fls`, `Wdg` |
| Custom · Nexteer in-house | Project-owned SW-Cs, drivers, services | `SF*`, `CF*`, `MM*`, `CM*`, `ES*`, `AR*` |
| Host tool / Integration | Build-time tooling or aggregated config | `TL*`, `_Ford_*`, `VectorBswSuprt` |

## Methodology (assumption, stated)

For each top-level module the **primary `src/*.c` header** (first 60 lines) was scanned:

1. `Vector Informatik` / `MICROSAR` and nothing else → **Vector-provided**.
2. `Renesas` → **Renesas-provided**.
3. `Nexteer` → **Custom** (RTE/generator headers under `tools/` that mention Vector
   identify the *generator*, e.g. “MICROSAR RTE Generator”, not the owner).
4. No marker → header-only/support folders checked (`include/`), else **Custom**
   (project glue) or **Tool/Integration** for folders without target sources.

Special cases are hardcoded and documented on their pages: `EcuC` (config only),
`Rte` (generator), `IoHwAb` (customised template), `VectorBswSuprt` (support bundle),
`TL*` (host tools with vendors where known).

## Limits

- Only the primary source header per module was sampled; individual files may differ.
- Generated files inside custom modules (e.g. `tools/contract/Rte_*.h`) are Vector
  *artefacts* but do not change module ownership.
- If you spot a misclassified module, the evidence note on its page shows exactly
  which file the decision was based on.
