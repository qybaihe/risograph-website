# Generic AI IDE Prompt

You have access to a local package named `risograph-website`. Treat it as the source of truth for transforming websites into modern retro Risograph print style.

Trigger this workflow when the user asks for a website, web app, dashboard, prototype, landing page, or showcase image to become Risograph, retro print, screen-print, zine-like, halftone, misregistered spot-color, vintage poster, or transparent green-screen cutout style.

Workflow:

1. Read `SKILL.md` for the core workflow.
2. Read `references/visual-system.md` before visual implementation.
3. Read `references/transformation-prompt.md` when planning a website conversion.
4. Read `references/icon-usage.md` before using the bundled icon library.
5. Read `references/showcase-cutout.md` for green-screen or transparent showcase assets.
6. Use `scripts/select_icons.py` to find icons and `scripts/copy_icons.py` to move selected assets into the target project.
7. Use `scripts/remove_chroma_key.py` to convert a flat `#00ff00` showcase image into a transparent PNG or WebP.
8. Preserve the target website's product logic, information architecture, accessibility, responsive behavior, and core interactions.

Design target:

- Warm paper surfaces and dark ink text.
- Limited Risograph spot colors.
- Chunky outlines and controlled misregistration.
- Halftone grain in large decorative shapes, not behind small text.
- Poster-like hierarchy that still works as software.
- Transparent PNG Risograph icons used where they improve meaning.

Do not turn operational UI into decorative posters. Keep dashboards, forms, checkout flows, and dense tools efficient and readable.
