# Image placement

Choose how the image participates in the interface before generating or cropping it. These are layout behaviors, not visual style recipes.

## Placement modes

### Full-bleed environment

Use a complete scene as the window background. This works for architecture, landscape, atmosphere, or artwork whose edges are expendable. Prepare a 16:10 master at 2560×1600 or larger, use cover-style cropping, and keep all meaningful subjects outside the measured native content zone.

### Anchored hero

Use for a recognizable character, artwork, object, or group. Composite the subject into a complete background canvas and keep the group compact near one outer edge. Preserve empty environment between the subject and native content. Do not merely shift `focalPoint`; crop alignment cannot repair a subject that was composed through the title, suggestion cards, or composer.

### Cutout foreground

Use a transparent character or object only when the target renderer explicitly supports a separate foreground layer with contain-style sizing and edge anchoring. Never feed a transparent cutout to a full-bleed cover background and assume transparent pixels, scale, or alignment will behave consistently. When foreground-layer support is unknown, composite the cutout onto a complete 16:10 background first.

### Texture field

Use for paper, grain, paint, clouds, fabric, or other imagery without one essential subject. The artwork may cover the window more freely, but keep contrast and spatial frequency low behind text, code, and controls.

### State-specific pair

Use a stronger home hero and a quieter task background only when the renderer supports route-aware assets. If it does not, produce one universal low-noise image that remains usable on task pages. Never claim state-specific behavior from a manifest that the renderer ignores.

## Crop math

`cover` fills the container and crops whichever source dimension overflows. Compare source and viewport aspect ratios before approval:

```text
visible horizontal fraction = viewport aspect ratio / source aspect ratio
```

Use this only when the source is wider than the viewport. A 2.50:1 source in a 16:10 viewport shows about 64% of its width and crops about 36%. `focalPoint` chooses which 64% survives; it cannot preserve both edges.

## Required workflow

1. Inspect the actual source dimensions and aspect ratio.
2. Choose one placement mode.
3. Mark the native title/cards zone, sidebar, task content, and composer on an actual Codex screenshot or faithful mock.
4. Generate or composite the artwork for that measured canvas.
5. Preview the crop matrix in `qa.md`.
6. Repair the source composition before tuning opacity or contrast.

Treat placement as unverified until the actual target renderer or a faithful crop simulation has been inspected. A contrast check and a valid `skin.json` are not enough.
