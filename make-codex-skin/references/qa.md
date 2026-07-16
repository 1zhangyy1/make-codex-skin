# Skin QA

Complete these checks before presenting a skin as finished.

## Package

- `skin.json` parses and its id matches the directory.
- Assets are local, supported, and rights-safe.
- The folder contains no executable content, symlinks, remote URLs, or unknown files.

## Readability

- Primary text reaches at least 4.5:1 contrast against background and surface.
- Muted text remains readable without competing with primary text.
- Code, diffs, status colors, approvals, and the composer remain distinguishable.
- Light skins avoid glare and dark skins avoid crushed surfaces.

## Composition

- Native content sits in a quiet region.
- The focal subject is not cut awkwardly or hidden behind the composer.
- Task content is stronger than background artwork.
- Sidebar detail does not fight navigation and task titles.
- The design has one protagonist and one coherent material language.

For raster artwork, also inspect:

- Home at 1440×900, 1280×800, and 1024×768.
- A real task state at a wide and a smaller viewport.
- Sidebar expanded and any supported collapsed state.
- Every meaningful face, hand, object, and artwork edge after `cover` cropping.
- Native title, suggestion cards, composer, menus, and long-form task content.

Fail the skin if a meaningful subject intersects native text or controls, if the composition relies on transparent pixels becoming a specific color, or if a crop removes context required to understand the artwork.

## Interaction assumptions

- Decorative layers must be non-interactive.
- Native controls, scrolling, selection, menus, and focus must remain usable.
- Motion must stop under reduced-motion preferences.

If these were not checked in a real renderer, label them as design requirements rather than verified facts.

## Repair order

Fix safety, readability, composer hierarchy, artwork collision, palette cohesion, and then decorative polish. Preserve the skin's distinct identity while repairing the smallest responsible dimension.
