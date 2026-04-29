---
name: risograph-website
description: "Transform existing or new websites, web apps, landing pages, dashboards, UI prototypes, and site showcase mockups into a retro Risograph print style. Use when Codex is asked to make a site Risograph, retro print, screen-print, zine-like, halftone, misregistered spot-color, vintage poster, or to package a website into a transparent green-screen cutout showcase using the bundled Risograph icon library."
---

# Risograph Website

Use this skill to restyle a website into a product-grade retro Risograph print experience while preserving its product logic, information architecture, accessibility, and core interactions.

## Core Workflow

1. Inspect the target website structure, framework, asset pipeline, existing design tokens, and icon system.
2. Read `references/visual-system.md` before making visual decisions.
3. Read `references/transformation-prompt.md` when planning the redesign direction or writing implementation notes.
4. Read `references/icon-usage.md` before selecting or copying bundled icons.
5. Read `references/showcase-cutout.md` when the user wants a website presentation mockup, app-store visual, social post image, or green-screen transparent showcase.
6. Choose semantically matched icons from `assets/risograph-icons-160/wiki/icon-wiki.tsv` or use `scripts/select_icons.py`.
7. Copy only the icons needed by the target website into its normal static asset folder with `scripts/copy_icons.py`.
8. Implement the visual system in the site's existing styling stack. Prefer CSS variables, design tokens, and reusable components over page-local one-off styles.
9. Verify responsive layout, text contrast, icon loading paths, and that the result feels tactile and printed without sacrificing UI clarity.

## Bundled Icon Library

The skill includes `assets/risograph-icons-160/`, a 160-icon transparent PNG library plus source green-screen sheets:

- `assets/risograph-icons-160/icons/`: transparent 512px PNG icons.
- `assets/risograph-icons-160/sheets/`: 10 source 4x4 green-screen sprite sheets.
- `assets/risograph-icons-160/wiki/icon-wiki.tsv`: source-of-truth icon metadata.
- `assets/risograph-icons-160/wiki/icon-manifest.json`: generated JSON manifest when available.
- `assets/risograph-icons-160/preview-transparent-icons-160.jpg`: full transparent icon preview.

Use icons as UI-supporting assets: feature cards, empty states, section headers, onboarding steps, help panels, print-poster hero accents, and controlled decorative moments. Do not replace every small system icon mechanically.

## Helper Scripts

Run scripts from the skill directory or pass explicit paths.

Build or refresh the JSON manifest:

```bash
python scripts/build_icon_manifest.py
```

Find icon candidates:

```bash
python scripts/select_icons.py --query "search filter settings" --limit 8
python scripts/select_icons.py --query "empty state upload file" --category "内容文件" --format json
```

Copy selected icons into a project:

```bash
python scripts/copy_icons.py \
  --slugs search filter-funnel settings-gear \
  --out /path/to/site/public/risograph-icons
```

## Implementation Rules

- Preserve the user's product and UX. Apply Risograph styling as a design system, not as a content rewrite.
- Use paper-like surfaces, dark ink outlines, spot-color blocks, halftone grain, slight registration offsets, overprint-like layers, and poster/zine composition.
- Keep text modern and readable. Texture belongs on large surfaces, icons, hero art, borders, and accents, not inside small body text.
- Use local bundled assets after copying them into the project. Do not reference the skill folder directly from runtime code.
- If the website already has a strong brand, blend Risograph materials with the brand instead of replacing all identity.
- For dashboards or dense apps, keep the layout quiet and efficient; use print texture for hierarchy, nav groups, empty states, and high-level modules.
- Avoid fake aged-paper grime, sepia-only palettes, low contrast ink on colored fields, decorative dots over text, photorealistic paper shadows, generic gradient orbs, and full-page texture noise.

## Verification

Before finishing:

- Confirm every copied icon path is referenced correctly.
- Confirm pages still work at mobile and desktop widths.
- Check that text does not overlap halftone fields, print marks, stickers, or cutout shadows.
- Check color contrast on spot-color surfaces.
- If a green-screen showcase is generated, verify the source background is flat and the transparent PNG has transparent corners.
- If a dev server is appropriate, run it and inspect the result in a browser or screenshot workflow.
