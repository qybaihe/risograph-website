# Risograph Website Adapter

Use the local `risograph-website` package as a portable AI design skill for converting websites into modern retro Risograph print style.

When a user asks for Risograph, retro print, screen-print, zine-like, halftone, misregistered spot-color, vintage poster, or transparent green-screen website showcase work:

1. Read `risograph-website/SKILL.md`.
2. Read the specific reference file needed for the task:
   - `references/visual-system.md` for visual decisions.
   - `references/transformation-prompt.md` for website conversion planning.
   - `references/icon-usage.md` before selecting or copying icons.
   - `references/showcase-cutout.md` for green-screen or transparent showcase assets.
   - `references/website-patterns.md` for page-type patterns.
3. Use `scripts/select_icons.py` to find bundled icons and `scripts/copy_icons.py` to copy only the needed PNG files into the target project.
4. Use `scripts/remove_chroma_key.py` when the showcase source uses a flat green background.
5. Preserve the target site's product logic, content hierarchy, accessibility, and core interactions.
6. Implement through the target project's existing styling stack and asset pipeline.

Do not reference files from this package directly in production runtime code. Copy needed assets into the target project.
