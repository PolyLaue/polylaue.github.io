# Viewing Data

Double-click a series in the navigator to open it in the main window.
The label above the image shows the current series, scan number, and
scan position, and the status bar shows the pixel position and intensity
under the mouse (plus details of any predicted reflection being
hovered).

Right-clicking the image opens a context menu that, in addition to the
usual view options, provides:

- **set as background** — use the current image as the background image
  for the current series, or for every series in the current section.
- **perform saturation check** — mark saturated pixels.
- **set scan position coordinates** — configure the physical coordinates
  displayed for the scan positions.
- **set acquisition times** — configure computed frame times for the
  current section (see below).
- **set frame as time zero** — display frame times relative to the
  current frame (see below).

Background subtraction can be toggled via **Settings → Apply Background
Subtraction**.

## Frame times

The main window displays a time for the currently viewed frame. The time
comes from one of two sources:

- **Computed acquisition times.** If acquisition intervals are
  configured and applied for the current section, the time of each frame
  is computed from the frame period, the break between rows, and the
  break between scans. By default it is relative to the first frame of
  the current series.
- **File modification times.** Otherwise, the displayed time is the
  creation/modification time of the currently viewed file, relative to
  the first file of the section.

### Acquisition times

Right-click the image and choose **set acquisition times** to configure
the intervals (frame period, row break, and scan break, in seconds) for
the current section. The **Apply acquisition times** checkbox controls
whether the computed times are used.

The intervals and the checkbox are stored **per section**. A newly
created section starts with the checkbox unchecked; as a convenience,
the interval values from the last section you configured are pre-filled.

### Time zero

Right-click any frame and choose **set frame as time zero** to display
all frame times relative to that frame. This works with both time
sources — computed acquisition times and file modification times — and
each source keeps its own time zero, so toggling **Apply acquisition
times** does not mix them.

The time zero resets to the default (the first frame of the series, or
the first file of the section, respectively) whenever a different series
is loaded, and the computed time zero also resets when the interval
values are changed.
