<p align="center">
  <img src="assets/risograph-website-header.png" alt="Risograph Website - retro print style for any website" width="100%" />
</p>

<h1 align="center">Risograph Website</h1>

<p align="center">
  <strong>把任何网站包装成现代 Risograph 复古印刷风</strong><br />
  <strong>Turn any website into a modern retro Risograph print experience</strong>
</p>

<p align="center">
  <a href="#zh-cn"><img alt="中文" src="https://img.shields.io/badge/%E9%98%85%E8%AF%BB-%E4%B8%AD%E6%96%87-F05242?style=for-the-badge" /></a>
  <a href="#en"><img alt="English" src="https://img.shields.io/badge/Read-English-335CFF?style=for-the-badge" /></a>
</p>

<p align="center">
  Codex · Claude Code · Cursor · other AI coding agents / AI IDEs
</p>

---

<a id="zh-cn"></a>

## 中文

`risograph-website` 不是一个只给 Codex 用的提示词，而是一套可迁移的 **AI IDE 风格工程包**：`SKILL.md`、视觉系统、转换提示词、160 个透明 PNG 图标、绿幕展示图流程、语义选图脚本和抠像工具。

它可以被 Codex 原生作为 Skill 使用，也可以被 Claude Code、Cursor、Windsurf、Cline、OpenCode 等 AI 编程环境作为规则库、项目上下文或 Agent Skill 资产包使用。

### 它做什么

把现有网站、Web App、Landing Page、Dashboard 或 UI 原型转换成现代 Risograph 复古印刷风，同时保留原有的信息架构、产品逻辑、可访问性和核心交互。

风格目标包括：

- 暖纸底、深墨文字、粗线描边
- 朱红、暖黄、蓝、靛蓝、紫、粉等有限专色
- 轻微错版套色、低透明网点、Overprint 层次
- 印章标签、裁切标记、海报式分区
- 160 个透明 PNG Risograph 图标
- 绿幕展示图，方便后续抠成透明 PNG

### 适合用在

- 产品官网、Landing Page、作品集、课程页
- SaaS 工具、编辑器、控制台、Dashboard
- 表单、结账页、空状态、Onboarding
- App Store / 公众号 / 社交媒体用的网站展示图
- PPT / Pitch Deck / 发布海报视觉资产

### 目录结构

```text
risograph-website/
├── SKILL.md
├── agents/openai.yaml
├── adapters/
│   ├── CLAUDE.md
│   ├── cursor-rule.mdc
│   └── generic-agent-prompt.md
├── references/
│   ├── visual-system.md
│   ├── transformation-prompt.md
│   ├── icon-usage.md
│   ├── showcase-cutout.md
│   └── website-patterns.md
├── scripts/
│   ├── select_icons.py
│   ├── copy_icons.py
│   ├── build_icon_manifest.py
│   └── remove_chroma_key.py
└── assets/
    ├── risograph-website-header.png
    └── risograph-icons-160/
        ├── icons/
        ├── sheets/
        ├── prompts/sheet-prompts.md
        └── wiki/icon-wiki.tsv
```

### 安装与接入

Codex 原生 Skill：

```bash
cd ~/.codex/skills
git clone https://github.com/qybaihe/risograph-website.git
```

Claude Code / Claude：

```bash
git clone https://github.com/qybaihe/risograph-website.git
```

把 `adapters/CLAUDE.md` 的内容合并到目标项目的 `CLAUDE.md`，或让 Claude 读取本仓库的 `SKILL.md`、`references/`、`assets/` 和 `scripts/`。

Cursor：

```bash
git clone https://github.com/qybaihe/risograph-website.git
mkdir -p .cursor/rules
cp risograph-website/adapters/cursor-rule.mdc .cursor/rules/risograph-website.mdc
```

其他 AI IDE：

使用 `adapters/generic-agent-prompt.md` 作为系统提示词或项目规则，并让 Agent 读取本仓库资源。

### 最小使用示例

让 Agent 执行：

```text
用 risograph-website 把这个网站改成现代 Risograph 复古印刷风。保留现有功能，从内置图标库挑选语义匹配的图标，并生成可用于展示的透明抠像图。
```

按语义找图标：

```bash
python scripts/select_icons.py --query "dashboard analytics search" --limit 8
```

复制图标到目标项目：

```bash
python scripts/copy_icons.py \
  --slugs search chart-up settings-gear \
  --out ./public/risograph-icons \
  --manifest
```

把绿幕图抠成透明 PNG：

```bash
python scripts/remove_chroma_key.py \
  --input ./showcase-green.png \
  --out ./showcase-transparent.png \
  --auto-key border \
  --soft-matte \
  --transparent-threshold 12 \
  --opaque-threshold 220 \
  --despill
```

### 使用边界

好的 Risograph 网站应该像一张能工作的印刷品：有触感，但不妨碍任务完成。

请避免：

- 把页面做成旧羊皮纸或复古脏污风
- 在正文、小字、输入框、表格里铺满纹理
- 用低对比文字压在专色块上
- 用装饰挡住按钮、导航或产品截图
- 把 Dashboard 变成海报，牺牲扫描效率

---

<a id="en"></a>

## English

`risograph-website` is not a Codex-only prompt. It is a portable **AI IDE style engineering pack**: `SKILL.md`, visual-system references, transformation prompts, 160 transparent PNG icons, green-screen showcase guidance, semantic icon scripts, and a built-in chroma-key helper.

It works as a native Codex Skill, and it can also be used by Claude Code, Cursor, Windsurf, Cline, OpenCode, and other AI coding agents as a project rule pack, context bundle, or agent skill asset library.

### What it does

It transforms existing websites, web apps, landing pages, dashboards, or UI prototypes into a modern retro Risograph print style while preserving the original information architecture, product logic, accessibility, and core interactions.

The style target includes:

- Warm paper surfaces, dark ink text, chunky outlines
- Limited spot colors: vermilion, yellow, blue, indigo, violet, pink
- Slight color misregistration, low-opacity halftone fields, overprint layers
- Stamp labels, crop marks, poster-like sections
- 160 transparent PNG Risograph icons
- Green-screen website mockups for transparent PNG cutouts

### Best for

- Product sites, landing pages, portfolios, course pages
- SaaS tools, editors, consoles, dashboards
- Forms, checkout flows, empty states, onboarding
- Website showcase images for app stores, newsletters, social media, or decks
- Pitch decks, launch posters, and presentation visuals

### Repository layout

```text
risograph-website/
├── SKILL.md
├── agents/openai.yaml
├── adapters/
│   ├── CLAUDE.md
│   ├── cursor-rule.mdc
│   └── generic-agent-prompt.md
├── references/
│   ├── visual-system.md
│   ├── transformation-prompt.md
│   ├── icon-usage.md
│   ├── showcase-cutout.md
│   └── website-patterns.md
├── scripts/
│   ├── select_icons.py
│   ├── copy_icons.py
│   ├── build_icon_manifest.py
│   └── remove_chroma_key.py
└── assets/
    ├── risograph-website-header.png
    └── risograph-icons-160/
        ├── icons/
        ├── sheets/
        ├── prompts/sheet-prompts.md
        └── wiki/icon-wiki.tsv
```

### Install and connect

Native Codex Skill:

```bash
cd ~/.codex/skills
git clone https://github.com/qybaihe/risograph-website.git
```

Claude Code / Claude:

```bash
git clone https://github.com/qybaihe/risograph-website.git
```

Merge `adapters/CLAUDE.md` into your target project's `CLAUDE.md`, or ask Claude to read this repo's `SKILL.md`, `references/`, `assets/`, and `scripts/`.

Cursor:

```bash
git clone https://github.com/qybaihe/risograph-website.git
mkdir -p .cursor/rules
cp risograph-website/adapters/cursor-rule.mdc .cursor/rules/risograph-website.mdc
```

Other AI IDEs:

Use `adapters/generic-agent-prompt.md` as a system prompt or project rule, and expose this repository's resources to the agent.

### Quick usage

Ask your agent:

```text
Use risograph-website to transform this website into a modern retro Risograph print style. Preserve existing functionality, choose semantically matched bundled icons, and generate a transparent showcase cutout.
```

Search for icons semantically:

```bash
python scripts/select_icons.py --query "dashboard analytics search" --limit 8
```

Copy selected icons into a target website:

```bash
python scripts/copy_icons.py \
  --slugs search chart-up settings-gear \
  --out ./public/risograph-icons \
  --manifest
```

Remove the green-screen background:

```bash
python scripts/remove_chroma_key.py \
  --input ./showcase-green.png \
  --out ./showcase-transparent.png \
  --auto-key border \
  --soft-matte \
  --transparent-threshold 12 \
  --opaque-threshold 220 \
  --despill
```

### Guardrails

A good Risograph website should feel like printed software: tactile, memorable, and still easy to use.

Avoid:

- Old parchment or dirty vintage paper effects
- Texture behind body text, inputs, or table data
- Low-contrast text on spot-color fields
- Decorations covering buttons, navigation, or screenshots
- Turning dashboards into posters at the cost of scanability

## License

MIT. See [LICENSE](LICENSE).
