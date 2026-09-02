# Introduction

## System Requirements

- **Operating system:** Windows, macOS, or Linux
- **Python:** version 3.11 or newer (installed automatically when using
  conda)
- **Memory:** requirements depend on the size of the data and the
  indexing settings. If the indexing routine fails due to a lack of
  memory, see the notes on the *Resolution Limit* and *Conserve Memory*
  options in [Algorithms](algorithms.md).
- **Storage:** the scan images must be available on a locally accessible
  filesystem.

All other dependencies are installed automatically. See
[Getting Started](getting-started.md) for installation instructions.

## About PolyLaue

PolyLaue is a software package for analyzing Laue diffraction data collected
*in-situ* and *en-operando*. The primary goal of PolyLaue is identifying and
tracking selected crystals within a multigrain sample during compression in
diamond anvil cells (DAC). Possible results include:

- Direct observation of parent/product or liquid/solid interface propagation
  in 2D
- Determination of product or twin variants after phase transitions and
  deformational twinning
- Observation of the formation and redistribution of strain and defects of the
  crystal lattice due to pressure-induced processes, including elastic/plastic
  deformation, phase transitions, melting, and crystallization

PolyLaue was developed to replace software that was used previously [1-9].

Results obtained with PolyLaue are saved in HDF format and as NumPy arrays,
and, therefore, they can be used by other programs [10].

!!! note

    Very detailed tooltips are available if you hover the mouse over an item
    of the interface. The information in these tooltips is not duplicated in
    this documentation.

See the [References](references.md) page for the numbered citations used
throughout this documentation.
