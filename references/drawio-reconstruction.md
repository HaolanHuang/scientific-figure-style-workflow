# Draw.io reconstruction checklist

Read this reference only after the user approves the generated raster draft.

## Setup

- Use computer-use UI automation to open the local Draw.io app or browser instance the user has available.
- Keep the approved image open as a visual reference at a useful zoom. Set the Draw.io page size and orientation to match it.
- Establish a small style palette and text styles first so repeated elements stay consistent.

## Rebuild order

1. Page background and large panels.
2. Main groups or containers.
3. Content shapes and icons, using editable vector shapes where possible.
4. Connectors and arrowheads; route them after shapes are placed so they attach to ports cleanly.
5. Labels, equations, legends, and annotations.
6. Group repeated modules and name groups meaningfully for later editing.

## Fidelity checks

- Compare the page at the final intended viewing size, not only while zoomed in.
- Check overall proportions, reading direction, spacing rhythm, alignment, color roles, stroke weights, corner radii, arrow routing, and z-order.
- Check that every important label is editable text, every connector is an actual connector, and no essential content exists only in the raster background.
- Confirm that fonts render consistently on the user's machine; substitute a common font only when necessary and preserve hierarchy.
- Export a vector format such as SVG or PDF and inspect it for clipped text, missing arrowheads, blurry embedded images, and unexpected rasterization.

## Handoff

Deliver the `.drawio` source and requested exports. Mention which elements are editable and identify any unavoidable raster asset (for example, a supplied microscopy image or generated texture). Keep the approved raster beside the source as a visual reference, not as the sole figure content.
