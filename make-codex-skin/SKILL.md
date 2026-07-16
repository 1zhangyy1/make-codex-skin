---
name: make-codex-skin
description: Design, create, review, and refine data-only visual skin packages for the Codex desktop app from a text direction, reference image, or existing artwork. Use when a user asks to make Codex match a mood, art movement, cultural reference, material, character, image, or other visual direction; turn an image into a Codex skin concept; repair an unreadable skin; or prepare a shareable skin folder. Preserve the native Codex interface. This Skill creates skin assets and metadata but does not install, inject, or apply them to Codex.
---

# Make Codex Skin

Create a coherent Codex visual system, not a wallpaper pasted behind the app. Keep the native sidebar, task content, controls, and composer usable in every state.

## Route the request

- For a new skin, follow the complete workflow below.
- For supplied artwork, preserve its intended subject and derive the palette, material, and focal point from it.
- For a style reference, extract visual principles; do not copy embedded UI, text, logos, or unlicensed characters.
- For review or repair, read `references/qa.md` and change only the failed dimensions.
- For installation or live application, explain that this public Skill produces the skin package only. Do not modify Codex or improvise an injection method.

## Load the right references

- Read `references/codex-ui-anatomy.md` before the first design in a task or when composition is uncertain.
- Read `references/visual-workflow.md` when creating or adapting artwork and deriving a palette.
- Read `references/skin-format.md` before writing `skin.json` or preparing a shareable folder.
- Read `references/qa.md` before presenting a skin as complete.

## Create a skin

1. Write a compact brief from the user's words and references. Infer ordinary details when the direction is already clear.
2. Synthesize one strong art direction. Do not begin from a catalog of named styles or force the request into a known recipe.
3. Prepare artwork when it materially carries the identity. Preserve a quiet zone for native content and avoid fake controls, embedded text, logos, and watermarks.
4. Copy `assets/skin-template/` into a new directory named after the skin id. Edit the copy; never edit the bundled template in place.
5. Make palette, surfaces, typography, composition, artwork, and motion express the same idea. Protect readability before decorative polish.
6. Check the folder against `references/skin-format.md` and `references/qa.md`. If a compatible `codex-skin check` command already exists in the user's environment, run it; otherwise report that engine validation was not performed.
7. Fix every static failure. Do not weaken contrast, rights, or package restrictions to make a skin appear complete.
8. Return the skin directory, art direction, artwork provenance, static QA result, and any validation that actually ran.

## Apply creative judgment

- Let the user's language and references drive the visual system. Do not present a house-style menu.
- Think in relationships: hierarchy, space, light, tactile behavior, color temperature, rhythm, and contrast.
- Define the art direction before choosing manifest fields. Treat preset names as internal drawing primitives, never as the concept.
- If available primitives cannot carry the identity, use suitable original artwork or state the missing capability instead of substituting the nearest familiar theme.
- Give the interface one visual protagonist and reduce competition around the composer and long-form task content.
- Treat light skins as designed light interfaces, not inverted dark skins.
- Prefer restrained motion and honor reduced-motion preferences.

## Preserve safety boundaries

- Produce data and image assets only. Do not place JavaScript, CSS, HTML, shell scripts, executables, symlinks, or remote URLs inside a skin folder.
- Never modify, unpack, replace, or re-sign the official Codex app or `app.asar`.
- Treat full skins as an unofficial community experiment, not the official Appearance theme format.
- Do not claim that a skin was installed, applied, or live-verified when only files or a mock preview were created.
