# Masterpieces After Hours / 名画夜班

User direction:

> Make an art-exhibition skin where people from famous paintings are using computers.

The Skill translated that short idea into a specific visual system:

- a contemporary museum after closing time;
- the public-domain figures Mona Lisa, Girl with a Pearl Earring, and Vincent van Gogh;
- all subjects grouped on the right around blank, unbranded computers;
- quiet architecture across the left and lower center for native Codex content;
- warm bone surfaces with Vermeer blue as the interface accent;
- no embedded text, logos, fake UI, or continuous motion.

The background was created with OpenAI image generation. The figures are new interpretations of public-domain paintings, not copied image files. See `LICENSE.txt` for the current asset status.

The checked text contrast was `11.82:1` against the window background and `13.88:1` against the primary surface. Live rendering is outside the public Skill, so the repository preview is explicitly a sanitized mockup rather than proof of official Codex theme support.

## Placement finding

The first source image was `1983×793` (about `2.50:1`). A real external-renderer test showed that cover-style placement could crop the group and allow the native home title and suggestion cards to cross the figures. That result is a failed placement test, even though the package and contrast checks passed.

For a production revision, recompose the scene on a 16:10 canvas, make the three-person group smaller and more tightly anchored to the far right, and recheck every viewport listed in `references/qa.md`. The repository mock demonstrates the intended hierarchy; it does not certify the current raster asset across window sizes.
