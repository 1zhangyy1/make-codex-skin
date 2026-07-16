# Skin format

Copy `assets/skin-template/` to the requested output location, rename the directory to the skin id, and make `skin.id` match that directory name.

```text
skin-id/
├── skin.json
├── preview.png             optional
├── LICENSE.txt             optional
└── assets/
    └── background.png      optional
```

Keep the folder data-only. Supported artwork is PNG, JPEG, WebP, or AVIF. Do not include CSS, JavaScript, HTML, shell files, executables, symbolic links, or remote URLs.

## Identity

- Keep `schemaVersion` at `1.0.0` for this experimental format.
- Use a lowercase, hyphenated `id` that matches the directory.
- Use semantic `version` values such as `0.1.0`.
- Describe the actual direction in `summary`.
- Use `UNLICENSED` for private work whose redistribution rights are not cleared.
- Preserve compatibility values unless a trusted renderer has tested a newer target.

## Appearance

Provide eight six-digit hex colors: `background`, `surface`, `sidebar`, `text`, `muted`, `accent`, `accentSoft`, and `border`. Normal text must reach 4.5:1 contrast against background and surface.

Keep `system-mono` for code. Layout and procedural preset names are internal rendering primitives, not visual recipes. Choose them only after the art direction exists. If no primitive expresses the direction, use image artwork or report the missing capability.

For image artwork, keep the source inside `assets/` and describe normalized `focalPoint` and `safeArea` coordinates. Use blur, grain, glow, and motion deliberately rather than maximizing every value.

## Validation claims

Static inspection proves only that the folder is coherent by the checks actually performed. A mock preview does not prove live Codex compatibility. An installed `codex-skin check` command may provide engine validation, but this Skill does not bundle or imply one.

Share the complete folder or a normal ZIP. Never bundle an installer or renderer executable inside an individual skin.
