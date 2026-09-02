# Mapping

PolyLaue can build maps of a small region of the frames across all scan
positions, which is useful for visualizing how a reflection (or any
region of interest) evolves across a scan.

## Region maps

Open **Mapping → Regions** to manage plain rectangular regions. Add a
region, position and resize it on the image, and click **Display Region**
to open a map of that region across the scan.

## HKL region maps

Open **Mapping → HKL Regions** to manage regions that are tied to a
specific reflection: each entry has a crystal ID and an HKL, and the
region automatically re-centers itself on that reflection's predicted
position whenever the scan number changes.

There are two ways to add an entry:

- Click **Add Region** in the dialog, then edit the crystal ID and the
  H, K, L values in the table. The region appears on the image as soon
  as the HKL can be resolved for the current scan.
- **Right-click a predicted reflection** on the image and choose
  *Create HKL map for (h k l)*. This opens the HKL Regions dialog and
  adds an entry for that reflection's crystal ID and HKL, centered on
  the reflection.

Predicted reflections must be loaded (see the Overlays menu) for HKL
regions to resolve their positions.

## Map windows

Clicking **Display Region** opens a map window for the selected region.
A map window can be **locked** to its current scan number, so that maps
of the same region at different scan numbers can be compared side by
side; displaying the region again then opens an additional, unlocked
window.
