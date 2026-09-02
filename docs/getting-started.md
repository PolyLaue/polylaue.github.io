# Getting Started

## Installation (conda)

First, create and activate a new conda environment for PolyLaue:

```bash
conda create -n polylaue -y
conda activate polylaue
```

Next, install Python 3.11 and the latest PolyLaue release into the conda
environment:

```bash
conda install -y -c conda-forge python=3.11 polylaue
```

You should be able to start PolyLaue now by running the `polylaue` command.

When a new terminal is opened, first activate the PolyLaue environment by
running `conda activate polylaue`, and then run the `polylaue` command to
start the application again.

To update PolyLaue to the latest version, activate the environment and run:

```bash
conda update -c conda-forge polylaue
```

## Installation (from source)

PolyLaue may also be installed from source with pip, using Python 3.11 or
newer:

```bash
git clone https://github.com/polylaue/polylaue
pip install ./polylaue
```

## First steps

After starting PolyLaue, the typical workflow is:

1. Create a project, a section, and one or more series pointing to your
   scan data — see
   [Projects, Sections, and Series](projects.md).
2. Double-click a series in the navigator to open it, and navigate
   between scans, scan positions, and frames — see
   [Viewing Data](viewing.md).
3. Overlay predicted reflections, pick points, and run the indexing and
   tracking routines — see [Picking Points](point-picking.md) and
   [Algorithms](algorithms.md).
4. Create region maps and HKL region maps — see [Mapping](mapping.md).

!!! note

    Very detailed tooltips are available if you hover the mouse over an
    item of the interface. The information in these tooltips is not
    duplicated in this documentation.
