# Picking Points

Several routines take a list of picked points (observed Laue spots) as
input. The same point-selection interface is used in three places:

- **Indexing → Select Points**, for picking points on their own,
- inside the **Find** interface (**Indexing → Find**), and
- inside the **Track/Refine** interface (**Indexing → Track/Refine**).

While the interface is active, **left-click** on the image adds a point
and **right-click** removes the nearest point. The dialog shows the
current number of points.

When picking points on their own via **Select Points**, the selection
can be saved as **Indexing** (`indexing.xy` at the root of the project
directory), **Refinement** (`refinement.xy`), or to an arbitrary file.

## Auto-pick Points

The **Auto-pick Points** button finds Laue spots automatically. The
image is thresholded, dilated, and labeled, and the weighted centroid of
each spot becomes a picked point. The threshold range, maximum
threshold, minimum area, and dilation radius can be adjusted
interactively, and the resulting points update live.

It is recommended to manually pick at least one point before
auto-picking, to help ensure the subsequent orientation-finding
algorithms will succeed.

Auto-pick may be run as many times as needed: each new run **replaces**
the points found by the previous auto-pick run, while manually picked
points are always kept. Canceling the auto-picker restores the points
exactly as they were before the run. The **Clear Points** button in the
Find and Track/Refine interfaces removes all points, manual and
auto-picked alike.
