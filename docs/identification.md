# Identifying and Tracking Crystals

This page follows the workflow for identifying a crystal of interest
within a multigrain sample, finding its orientation, and tracking it
across a series of scans. The point-picking interface used by Find and
Track/Refine is described on the [Picking Points](point-picking.md)
page, and the algorithms on the [Algorithms](algorithms.md) page.

## Mapping of Laue reflections

Select a crystal of interest by mapping Laue spots. Open **Mapping →
Regions**, click **Start Interactive Add**, and draw a region around a
Laue spot on the image:

![The Mapping menu](img/mapping-menu.png)

![The Mapping Regions dialog](img/regions-start-add.png)

![A region drawn around a Laue spot](img/regions-draw.png)

Click Stop Interactive Add.

![The region listed in the table](img/regions-added.png)

Click Display Region.

![The map of the region](img/regions-map.png)

Click Show Map Shape and adjust the map size.

![Adjusting the map shape](img/regions-map-shape.png)

Shift the region of interest to the position of crystal of interest.

![The region shifted to the crystal of interest](img/regions-map-shifted.png)

Zoom in the region of interest.

![The map zoomed in on the region of interest](img/regions-map-zoom.png)

See the [Mapping](mapping.md) page for more on region maps.

## Finding crystal orientation

Laue spot selected by mapping is used as primary reflection to index other reflections produced by the same crystal. See the [Algorithms](algorithms.md) page for more details.

![The Indexing menu](img/indexing-menu.png)

Open Find interface and click on reflection preselected by mapping.

![The Find Orientation dialog](img/find-dialog.png)

Click Auto-pick Points, adjust peak search parameters and click OK.

![Auto-picked points](img/find-auto-pick.png)

Secondary points can be also picked up manually by clicking on reflections
before applying Auto-pick Points, if there is indication that those
reflections are produced by the same crystal as primary Laue spot, for
instance if those points belong to the same zone line as primary reflection.
Secondary points selected manually are processed before those selected by
Auto-pick Points in the same order as those points were selected. If
manually selected points indeed denote reflections produced by the same
crystal as primary reflection solution will be found faster.

![Manually picked secondary points on a zone line](img/find-manual-points.png)

In Find Orientation interface click Apply. Adjust parameters in the
interface and repeat this stage if needed until solution is found.

![The Burn Reflections dialog after a successful Find](img/find-burn.png)

![The console output of Find](img/find-output.png)

If no valid orientation is found, click Clear Crystal to simply delete that
crystal.

![Maps of indexed reflections must be consistent](img/find-maps-consistent.png)

## Tracking of crystals

Instead of saving crystal orientation with respect to the reference frame this routine saves angular shift with respect to the orientation matrix determined at different pressure. See the [Algorithms](algorithms.md) page for more details.

Shift to a later scan and open Track/Refine interface.

![Track/Refine in the Indexing menu](img/track-menu.png)

Click Auto-pick Points, adjust peak search parameters and click OK.

![Auto-picked points for tracking](img/track-auto-pick.png)

In Track/Refine interface click Apply. Adjust parameters in the interface
and repeat this stage if needed until solution is found.

![A successful track](img/track-succeeded.png)

![Burning the tracked reflections](img/track-burn.png)

Select structure type and adjust d-limit if needed: see [Visualization of predicted reflections](reflections.md#visualization-of-predicted-reflections).

When option Replace ABC Matrix is activated, instead of just recording the
angular shift for this scan number, PolyLaue replaces the ABC matrix in the
crystal with the result of this tracking, and recomputes all other angular
shifts with respect to the new ABC matrix. In other words, the new
abc-matrix calculated by track is saved on the current scan but the previous
matrix is used to get orientation matrices on the other scans based on saved
angular shifts and those abc-matrices, in turn, are used to calculate
updated angular shifts with respect to the new abc-matrix. This option is
beneficial if the scan where the ABC matrix was initially indexed is not
going to be used anymore.

When angular shift approaches 30°, option “Use nearest tracked scan for reference ABC matrix” may need to be activated in order to avoid uncertainty introduced by the symmetry of translation lattice: see the tooltip and the [Algorithms](algorithms.md#tracking-of-crystals) page for more details. This option may be also beneficial to make the procedure faster by reducing the Angular Limit.

## Tracking within the current scan

This feature is for measuring properties such as crystal bending, where
different scan positions on the same scan number have different orientations
for the same crystal. Activate "Track within this scan" checkbox in the
"Track Orientation" dialog. There is a detailed tooltip if you hover your
mouse over it.

It is more efficient to select reflections from current crystal manually.

![The Track within this scan checkbox](img/track-within-scan.png)

After it finishes, it reports the angular shift in degrees.

![The reported angular shift](img/track-within-scan-result.png)

It does not save the ABC matrix or angular shift in the HDF5 file. However,
it does use the new ABC matrix to burn reflections. It pops up the "Burn
Reflections" dialog, where there's a checkbox at the bottom named "Use
Custom Internal ABC Matrix" that will be checked and will already have the
ABC matrix from the track stored internally. If you hover your mouse over
it, it shows the ABC matrix. Using button Save as New Crystal will save the
ABC matrix as a new crystal in HDF5 file. This capability can be useful to
identify split crystals.

![The Burn Reflections dialog with the custom internal ABC matrix](img/track-within-scan-burn.png)

## Refinement of crystal orientation

Repeating of tracking with smaller angular tolerance and smaller d-limit
will overwrite the prior angular shift with the new one. PolyLaue does not
take into account the previous angular shift at all - it just performs
tracking from the crystal's orientation matrix (based upon whichever scan
was used to generate it) in order to determine the angular shift matrix that
best fits the picks.

![Refining an orientation with Track/Refine](img/refine.png)

## Tracking on the scan where the original ABC matrix is stored

![The warning when tracking on the original scan](img/track-original-scan.png)

If select "Yes", it will automatically check "Replace ABC Matrix?" before
running, and then it replaces the ABC matrix, including recalculating all
other angular shifts so that they don't change.

![The result of tracking on the original scan](img/track-original-scan-result.png)

