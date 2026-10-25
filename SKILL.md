---
name: scientific-figure-style-workflow
description: "Create original scientific overview, method-flow, and schematic figures from a reference image's visual language, then iterate with user feedback and reproduce the approved result as editable Draw.io vector artwork. Use Python plotting directly for quantitative bar, line, scatter, pie, or similar charts."
---

# Scientific figure style workflow

Use this skill for paper-style overview figures, method pipelines, conceptual schematics, graphical abstracts, and other diagrammatic scientific artwork. Route ordinary quantitative charts to Python plotting instead. The user may supply a reference image, ask the Plot Is All You Need GitHub skill to help choose one, or provide both.

The reference skill is the public repository [liouhai/plot-is-all-you-need](https://github.com/liouhai/plot-is-all-you-need). When installed, invoke it as `$plot-is-all-you-need` (or its `/plot-is-all-you-need:plot` entry point); its gallery/contact-sheet workflow is useful for visual selection even when the final deliverable is a scientific diagram. Respect its `THIRD_PARTY_NOTICES.md` when retaining or redistributing reference assets.

## Operating contract

- Treat the reference as a guide to composition, visual grammar, palette, typography hierarchy, icon treatment, line weight, whitespace, and level of detail. Create an original figure containing the user's own scientific content.
- Do not invent scientific content, labels, datasets, model components, or causal claims. If the content needed to draw the figure is missing, pause and ask for it before image generation. Ask only for the smallest set of missing facts needed to proceed.
- Keep the interaction iterative. After every generated image, show or link the artifact and ask for targeted feedback. Do not move to Draw.io reconstruction until the user explicitly says the image is approved or equivalent.
- Keep a provenance note in the working output: reference image supplied or selected, user-provided content, generated draft versions, and final approval state. Do not copy publication logos, watermarks, or paper-specific text unless the user explicitly provides rights and asks for it.

## Workflow

1. **Classify and select a reference.** Decide whether the request is diagrammatic or quantitative. For diagrammatic work, invoke `$plot-is-all-you-need` when available and ask it to show a gallery/contact sheet for an overview, method-flow, or schematic reference; the user can select one image or combine attributes such as “B's layout + E's palette.” If the skill is unavailable, ask for the repository/link or use a user-supplied image. For quantitative bar, line, scatter, histogram, heatmap, pie, or similar data plots, use Python plotting and skip image generation and Draw.io.
2. **Inspect the reference.** Extract a compact style brief: canvas aspect ratio, panel hierarchy, reading direction, layout primitives, palette, fills/gradients, stroke and arrow conventions, typography, icon/illustration style, annotation density, and what makes the figure legible at paper scale. Preserve only reusable visual characteristics, not the original scientific claims.
3. **Collect the user's figure specification.** Confirm the purpose, audience, required entities and relationships, process order, labels or equations, desired aspect ratio/output size, and any must-keep colors or terminology. Use the intake checklist in [references/intake-and-figure-routing.md](references/intake-and-figure-routing.md). If the user has not provided the content, ask before calling image generation.
4. **Generate an original draft.** Invoke the image-generation capability with the style brief plus the user's content specification. Explicitly request a clean scientific figure, readable labels, coherent arrows, and original symbols. When exact text rendering is unreliable, keep labels short and plan to correct them during Draw.io reconstruction. Save each draft with a version number and keep the prompt/style brief alongside it.
5. **Iterate from feedback.** Present the draft and ask what to change. Apply requested changes to content, layout, color, legibility, or emphasis; regenerate only the affected aspects where possible. Repeat until the user approves the image. If feedback is ambiguous, ask a focused choice question rather than guessing a scientific relationship.
6. **Reconstruct in Draw.io after approval.** Use computer-use UI automation to open the user's local Draw.io, create editable vector shapes, connectors, text, and groups, and reproduce the approved layout. Follow [references/drawio-reconstruction.md](references/drawio-reconstruction.md). Keep a high-resolution raster reference visible while rebuilding, but redraw every editable element. Verify alignment, text, arrowheads, z-order, spacing, and export quality before delivering the `.drawio` file and an exported SVG/PDF/PNG when requested.

## Tool routing and stopping points

- Plot Is All You Need: reference discovery and selection only.
- Python plotting: numeric charts and data-driven statistical graphics.
- Image generation: original diagrammatic draft after content and style are confirmed.
- Computer use: local Draw.io reconstruction only after explicit user approval of the generated image.
- If a tool is unavailable, report the exact missing capability and preserve the current draft/specification so the workflow can resume; do not silently substitute a different visual medium.

For detailed intake questions and classification examples, read [references/intake-and-figure-routing.md](references/intake-and-figure-routing.md). For the editable-vector handoff, read [references/drawio-reconstruction.md](references/drawio-reconstruction.md).
