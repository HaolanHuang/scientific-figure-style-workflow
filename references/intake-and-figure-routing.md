# Intake and figure routing

Use this reference when the request is underspecified or the desired output type is unclear.

## Classify the requested visual

Route to Python when the figure encodes measured or simulated values through axes, ticks, legends, statistical marks, or a numeric color scale: bar, line, scatter, box/violin, histogram, pie/donut, heatmap, ROC/PR, forest plot, or similar.

Route to the diagram workflow when the figure explains entities, mechanisms, architecture, a process, a model pipeline, a biological pathway, an experiment overview, or a conceptual relationship. A diagram can contain small quantitative insets; use Python for those insets and combine them only if the user asks.

## Minimum content brief

Ask for the missing items in this order:

1. **Purpose:** What should a reader understand in five seconds?
2. **Entities:** The objects, modules, stages, actors, or datasets that must appear.
3. **Relationships:** Arrows, data flow, grouping, hierarchy, feedback loops, or spatial relations.
4. **Text:** Exact labels, abbreviations, equations, and terminology that must be preserved.
5. **Emphasis:** The main contribution or visual focal point.
6. **Output:** Target aspect ratio, approximate size, background, and whether the final editable file must be Draw.io.

If only a reference image is provided, do not infer the user's method from it. Ask for a content brief. If only a content brief is provided, ask for a reference image or permission to choose one through Plot Is All You Need.

## Style extraction fields

Record these fields in the working notes before generation:

- composition and reading direction;
- panel or stage count and relative area;
- palette with semantic roles (background, primary, secondary, highlight, warning);
- shape language (rounded cards, capsules, organic blobs, isometric blocks, pictograms);
- connector language (straight, orthogonal, curved, dashed, arrowhead style);
- typography hierarchy and label density;
- rendering treatment (flat, soft gradient, glass-like, hand-drawn, 3D, texture);
- whitespace, border, and alignment rules.

Use these as constraints in the image prompt. Keep scientific symbols and labels supplied by the user exact; shorten only with explicit approval.

## Feedback loop

After each draft, ask for one or more concrete changes such as “move the encoder above the decoder,” “use the reference's muted blue palette,” “make the central contribution larger,” or “replace the icon with a cell schematic.” Track them as a short change list and regenerate a new version. Approval means the user explicitly accepts the visual as the source of truth for Draw.io reconstruction.
