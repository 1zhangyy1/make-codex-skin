<div align="center">

# Make Codex Skin

### Describe a feeling. Let AI design the skin.

A small, open-source Skill that teaches Codex how to turn an open-ended visual direction into a coherent, readable Codex desktop skin package.

English · [简体中文](./README.zh-CN.md)

</div>

![Masterpieces After Hours shown in a sanitized mock preview](./docs/masterpieces-after-hours-preview.jpg)

## One repository, one Skill

This repository intentionally contains no website, theme gallery, npm project, installer, injection engine, or catalog of fixed styles.

The Skill helps AI:

- understand a mood, art reference, image, material, or cultural direction;
- synthesize an original visual system instead of choosing a preset style;
- design the palette, surfaces, composition, artwork, typography, and motion together;
- protect the sidebar, task content, code, controls, and composer;
- create a data-only skin folder that can be inspected and shared safely.

It does **not** modify Codex, patch `app.asar`, restart the app, or claim to be an official OpenAI theme system. Live application belongs to a separate trusted renderer and is outside this first public release.

## Install

```bash
git clone https://github.com/1zhangyy1/make-codex-skin.git make-codex-skin-repo
mkdir -p ~/.codex/skills
cp -R make-codex-skin-repo/make-codex-skin ~/.codex/skills/
```

Restart Codex if the new Skill does not appear immediately.

## Use

Ask naturally:

```text
Use $make-codex-skin to create a French romantic skin with the atmosphere
of a quiet Left Bank atelier. Keep it warm, artistic, and easy to read.
```

You can also provide an image, ask for an unfamiliar artistic direction, or ask the Skill to repair an existing skin without erasing its identity.

The result is a folder like this:

```text
my-skin/
├── skin.json
├── preview.png          optional
├── LICENSE.txt          optional
└── assets/
    └── background.png   optional
```

Two inspectable results are included:

- [`make-codex-skin/examples/parisian-atelier`](./make-codex-skin/examples/parisian-atelier/) — a procedural skin derived from a French romantic direction.
- [`make-codex-skin/examples/masterpieces-after-hours`](./make-codex-skin/examples/masterpieces-after-hours/) — an image-based skin derived from “people from famous paintings using computers.”

They demonstrate the workflow; neither is a recipe the AI must follow.

## Image-based example: Masterpieces After Hours

The short request was:

> Make an art-exhibition skin where people from famous paintings are using computers.

The Skill turned it into a museum after closing time, with new interpretations of Mona Lisa, the Girl with a Pearl Earring, and Vincent van Gogh grouped on the right around blank computers. The left side and lower center remain quiet for native Codex content.

The artwork was generated for this project with OpenAI image generation. The figures reinterpret public-domain paintings; no third-party painting files, logos, screen text, or fake UI were embedded. The image asset remains `UNLICENSED` until the creator chooses explicit reuse terms.

The preview above is a sanitized mockup made for the repository. It contains no private Codex tasks and is not proof of official theme support or one-click installation.

Image placement is part of the skin design, not a final coordinate tweak. The Skill now distinguishes full-bleed environments, anchored heroes, transparent foreground cutouts, texture fields, and route-specific home/task pairs. It also requires crop testing at multiple window sizes. See [`image-placement.md`](./make-codex-skin/references/image-placement.md).

The current Masterpieces source is intentionally documented as a placement finding: its ultra-wide `2.50:1` canvas can crop aggressively in a normal Codex window. The mock shows the target hierarchy, while the example notes record that the raster still needs a 16:10 production recompose before it can be treated as cross-window ready.

## How the Skill thinks

```text
your words or reference
          ↓
understand tone, space, light, material, rhythm
          ↓
synthesize one coherent art direction
          ↓
map it to readable UI and local artwork
          ↓
deliver a data-only skin folder + honest QA notes
```

Creative decisions remain high-freedom. Package structure, readability, rights, and safety remain strict.

## Repository map

```text
make-codex-skin/          the installable Skill, including two examples
docs/                     sanitized README preview
README.md                 English project page
README.zh-CN.md           Chinese project page
LICENSE                   MIT
```

## Current boundary

This v0.1 proves that AI can be taught to design varied Codex skins without a closed menu of visual recipes. It does not yet solve one-click installation or cross-version live rendering.

The output format is an experimental community format, not the official Codex Appearance theme format. Never redistribute artwork, characters, logos, photos, or fonts without the appropriate rights.

## Inspiration and references

This project was inspired in part by [Fei-Away/Codex-Dream-Skin](https://github.com/Fei-Away/Codex-Dream-Skin), which demonstrated that an external renderer can keep native Codex controls interactive while using a dedicated home image, a lower-noise task background, loopback CDP, and a restore path. Its macOS documentation also recommends wide images of at least 2000 px and keeping native content zones calm.

`make-codex-skin` is an independent AI creation Skill and experimental data format. It does not copy, bundle, install, or claim drop-in compatibility with the Codex Dream Skin engine. Thanks to Fei-Away and contributors for making the practical rendering approach visible to the community.

## License

The Skill and original documentation are available under the [MIT License](./LICENSE). Example artwork or contributed assets may declare their own license.

“OpenAI” and “Codex” are trademarks of their respective owner. This independent project is not affiliated with, endorsed by, or supported by OpenAI.
