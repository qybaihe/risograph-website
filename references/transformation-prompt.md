# Transformation Prompt

Use this as the redesign brief when planning or implementing a website conversion:

```text
Preserve the website's information architecture, content priority, conversion goals, and core interactions. Redesign the visual system into a retro Risograph print product style: warm paper surfaces, chunky dark ink outlines, limited spot-color palette, halftone grain clipped inside large shapes, slight red/blue/yellow registration offsets, overprint-like layers, stamp labels, bundled local Risograph icons, and restrained tactile motion. The result should feel like a polished zine/poster-inspired product interface, not a dusty antique page or a decorative poster that makes the UI harder to use.

Replace or add icons only where the bundled Risograph icons improve meaning. Use paper texture, halftone blocks, and print marks as hierarchy and atmosphere, never as clutter. Avoid low contrast, sepia-only palettes, fake paper grime, decorative dots over text, generic gradients, and hiding product screenshots behind texture.
```

## Practical Conversion Steps

1. Identify the target site's product type: landing page, dashboard, content site, tool, form, checkout, portfolio, prototype, or showcase.
2. Define design tokens: base paper, panel paper, ink, muted, line, red, yellow, blue, indigo, violet, pink, shadow.
3. Convert global background, typography, and surfaces before touching individual components.
4. Restyle navigation, buttons, cards, forms, tables, badges, section dividers, and empty states.
5. Add halftone and paper texture through CSS pseudo-elements, masks, or small repeated backgrounds, with opacity low enough for readability.
6. Select icons only after hierarchy is stable.
7. Add one or two controlled Risograph motifs per page: offset shadow, stamp badge, halftone band, print frame, cutout icon, or overprint shape.
8. Check mobile layout. Remove decorative marks on narrow screens when they compete with content.

## Tone Calibration

Product-grade Risograph:

- Warm paper, clear panels, restrained halftone, and readable controls.
- Best default for SaaS, tools, dashboards, and operational apps.

Editorial Risograph:

- Larger headings, poster bands, more asymmetry, bigger icon or screenshot moments.
- Best for landing pages, portfolios, events, education, and creative brands.

Indie Zine UI:

- More hand-cut labels, stamp marks, offset icons, and playful texture.
- Best for personal tools, creative apps, cultural projects, games, and non-serious workflows.

## Stop Conditions

Pause and reassess if:

- Text starts overlapping texture or print marks.
- Texture is visible inside small controls or body text.
- More than three spot colors compete in one compact component.
- Tables, forms, or checkout flows become harder to scan.
- The result reads as a static poster rather than an interactive website.
