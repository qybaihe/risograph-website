# Icon Usage

## Selection

Start from the Wiki:

```text
assets/risograph-icons-160/wiki/icon-wiki.tsv
```

Fields:

- `slug`: stable filename stem.
- `name`: display name.
- `category`: semantic group.
- `description`: visual description.
- `use_when`: usage keywords when present.
- `icon_path`: path relative to `assets/risograph-icons-160/`.

Use `scripts/select_icons.py` for quick matching. It searches slug, name, category, description, and use_when.

## Copying

Copy icons into the target project; do not reference the source skill/package folder from runtime code. The source may live in `~/.codex/skills/...`, a cloned `risograph-website/` folder, or another AI IDE workspace path.

Common destinations:

- Vite/React/Next static files: `public/risograph-icons/`
- Bundled React assets: `src/assets/risograph-icons/`
- Plain HTML: `assets/risograph-icons/`

Prefer keeping filenames as `<slug>.png`.

## Usage Patterns

Use icons for:

- Feature cards: one icon per card.
- Empty states: one larger icon plus short text.
- Section headers: one icon beside a heading.
- Navigation groups: 20px-32px icons.
- Onboarding steps: 48px-96px icons.
- Hero or poster motifs: 80px-180px icons, not behind body text.
- Tool buttons: only where a familiar symbol remains clear.
- Social or launch visuals: icon clusters around the product screenshot.

Avoid:

- Replacing every tiny system icon.
- Using icons as wallpaper.
- Scaling 512px PNGs so large that raster edges become obvious.
- Putting icons behind form labels, table data, or dense text.
- Mixing this icon style with unrelated icon packs unless there is a transition plan.

## Category Hints

- 核心状态: success, warning, info, help, visibility, fire, star.
- 导航控制: home, menu, search, settings, dashboard, list, tabs, sidebar.
- 方向动作: upload, download, share, refresh, undo, redo, sort, shuffle.
- 内容文件: documents, folders, notes, calendar, receipts, upload/download files.
- 媒体创作: image, video, camera, music, palette, brush, crop, layers.
- 沟通社交: chat, mail, phone, team, handshake, megaphone, link, support.
- 商业数据: cart, card, gift, ticket, badge, chart, target, delivery, store.
- 时间地点: clock, map, route, car, train, building, destination, signpost.
- 科技安全: terminal, code, database, cloud, wifi, lock, shield, robot.
- 生活装饰: coffee, plant, leaf, wave, flower, ribbon, burst, tape, splash.
