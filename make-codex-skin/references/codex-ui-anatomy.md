# Codex UI anatomy

Use the official Codex desktop app as the product and interaction baseline. A skin may change atmosphere and material, but it must not invent a replacement interface.

## Functional regions

- **Shell:** artwork may span the window, but content surfaces must remain readable above it.
- **Sidebar:** keep projects, tasks, navigation, status, and selection states obvious. Avoid detailed artwork behind dense lists.
- **Home:** allow a stronger composition while reserving quiet space for native headings and suggestions.
- **Task:** reduce artwork contrast and motion so text, code, diffs, tool output, and approval controls dominate.
- **Composer:** give the primary action surface a stable edge, sufficient contrast, and a clear focus state.
- **Menus and settings:** use reliable opaque or strongly frosted surfaces. A skin is incomplete if only the home page works.

## Composition guidance

- Keep a broad low-detail area for native content. Measure it from the actual Codex renderer; do not assume that “left side calm” is sufficient because the home title and suggestion cards occupy the central main surface.
- Place a focal subject away from headings and the composer.
- Keep the lower central band calm.
- Let decorative lines, clouds, grain, or foliage exit the frame instead of ending in hard crops.

Treat these as relationships, not a fixed layout recipe. Verify the actual window and artwork when possible.

On the home state, treat the native title, suggestion cards, and composer as one protected composition rather than three unrelated elements. On task states, the readable work surface must dominate the artwork. If a face, hand, product, or other meaningful subject intersects native text or controls, the composition fails even when contrast passes.

## Invariants

Preserve readable text and code, pointer and keyboard behavior, focus and selection states, sidebar/main/composer hierarchy, reduced-motion behavior, and smaller supported windows.

Official Appearance controls and external full-skin experiments are not the same thing. Never describe background imagery or decorative layers as an official OpenAI theme API.
