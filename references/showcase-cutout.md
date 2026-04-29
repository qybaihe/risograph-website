# Green-Screen Showcase Cutout

Use this when the user wants to package a website, app screen, product page, or generated mockup into a Risograph-styled transparent presentation asset.

## Workflow

1. Capture or render the website screen at the needed viewport.
2. Create a showcase composition on a perfectly flat green `#00ff00` background:
   - website screenshot as the main subject;
   - warm paper frame or browser shell;
   - Risograph spot-color shadows, halftone shapes, stamp badges, and bundled icons around it;
   - generous padding so the subject does not touch the image edge.
3. Keep the green background flat, uniform, and unused inside the subject.
4. Remove the green background with the built-in chroma-key helper from the image generation skill.
5. Validate transparent corners, clean edges, and no visible green fringe.

## Showcase Prompt

```text
Create a polished transparent-ready website showcase mockup in retro Risograph print style on a perfectly flat solid #00ff00 chroma-key background. The background must be one uniform color with no shadows, gradients, texture, paper grain, reflections, or lighting variation.

Main subject: a website screenshot framed as a tactile printed browser poster, with warm off-white paper frame, chunky dark ink outline, subtle red/blue/yellow misregistration, halftone grain clipped inside decorative shapes, small crop marks, stamp-like labels with no readable text, and a few Risograph sticker icons around the frame. Keep the website content readable and do not cover important UI.

No green anywhere inside the subject. No cast shadow on the background, no floor plane, no watermark, no readable text added by the model unless provided exactly. Keep generous padding and crisp separated edges for chroma-key removal.
```

## Local Chroma-Key Removal

Use the installed helper:

```bash
python "${CODEX_HOME:-$HOME/.codex}/skills/.system/imagegen/scripts/remove_chroma_key.py" \
  --input <source-green-screen.png> \
  --out <transparent-showcase.png> \
  --auto-key border \
  --soft-matte \
  --transparent-threshold 12 \
  --opaque-threshold 220 \
  --despill
```

If a thin fringe remains, retry once with `--edge-contract 1`. Avoid native transparency fallback unless the user explicitly asks for it or chroma keying fails.

## Verification

- Corners must be transparent in the final PNG.
- The website screenshot must remain inspectable.
- Halftone texture and print marks must not cover body text or primary buttons.
- The output should work on light, dark, and colored backgrounds.
