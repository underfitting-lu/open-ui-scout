# Open UI Scout

<p align="center">
  <strong>给 AI Coding Agent 用的前端 UI 资源选择 Skill</strong>
</p>

<p align="center">
  先理解页面、产品气质、技术栈和约束，再从 GitHub 开源 UI 资源池里选择合适资源。
</p>

<p align="center">
  <a href="#中文">中文</a> · <a href="#english">English</a> · <a href="#快速开始">快速开始</a> · <a href="#第三方-ui-资源与许可证说明">许可证说明</a>
</p>

<p align="center">
  <img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-green">
  <img alt="Skill" src="https://img.shields.io/badge/agent-skill-blue">
  <img alt="UI Resource Scout" src="https://img.shields.io/badge/UI-resource%20scout-purple">
</p>

## 中文

Open UI Scout 是一个通用、可公开分享的前端 UI 选择 skill。它不是一个固定模板，也不是“永远用某个 UI 库”的规则，而是一套让 AI coding agent 在写前端之前先做判断的工作流。

它适合 Codex、Claude Code、Cursor、Windsurf、Gemini CLI 等 coding agents。

## 它解决什么问题

很多 AI 做前端时会直接跳进熟悉套路：黑紫科技风、卡片堆满屏、默认 shadcn/ui、随手混好几个 UI 库，最后页面看起来“能跑”，但不贴合产品。

Open UI Scout 让 agent 先回答这些问题：

- 这是什么页面？Dashboard、Landing Page、AI Chat、编辑器工作台、移动 H5，还是别的？
- 这个产品应该是什么气质？专业、温暖、极简、企业、学术、可爱、创作者工具？
- 当前项目已经用了什么技术栈和 UI 体系？
- 是否有许可证、可维护性、依赖体积、可访问性、响应式等生产约束？
- 该从哪些 GitHub 开源 UI 资源里选，最多选几个才不会混乱？

## 一句话工作流

```text
理解需求 -> 判断页面类型 -> 判断视觉气质 -> 检查现有技术栈 -> 评分候选资源 -> 最多选择 3 个主要 UI 来源 -> 生成一致的前端 UI
```

## 适合谁用

- 想让 AI 写出更有设计判断力前端的开发者
- 用 Codex、Claude Code、Cursor、Windsurf、Gemini CLI 做 vibe coding 的用户
- 不想每个页面都变成黑紫 AI 科技风的人
- 需要 agent 尊重现有设计系统和技术栈的团队
- 想快速从 GitHub 开源 UI 生态里挑对资源的人

## 安装

下面的命令可以直接复制运行。仓库默认分支是 `master`。

### Codex

安装到当前用户的 Codex skills 目录。

**macOS / Linux / Git Bash**

```bash
mkdir -p ~/.codex/skills/open-ui-scout
curl -L https://raw.githubusercontent.com/underfitting-lu/open-ui-scout/master/.claude/skills/open-ui-scout/SKILL.md \
  -o ~/.codex/skills/open-ui-scout/SKILL.md
```

**Windows PowerShell**

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.codex\skills\open-ui-scout"
Invoke-WebRequest `
  -Uri "https://raw.githubusercontent.com/underfitting-lu/open-ui-scout/master/.claude/skills/open-ui-scout/SKILL.md" `
  -OutFile "$env:USERPROFILE\.codex\skills\open-ui-scout\SKILL.md"
```

安装后重启 Codex，让新 skill 生效。

### Claude Code

安装到当前项目的 Claude Code skills 目录。

**macOS / Linux / Git Bash**

```bash
mkdir -p .claude/skills/open-ui-scout
curl -L https://raw.githubusercontent.com/underfitting-lu/open-ui-scout/master/.claude/skills/open-ui-scout/SKILL.md \
  -o .claude/skills/open-ui-scout/SKILL.md
```

**Windows PowerShell**

```powershell
New-Item -ItemType Directory -Force ".\.claude\skills\open-ui-scout"
Invoke-WebRequest `
  -Uri "https://raw.githubusercontent.com/underfitting-lu/open-ui-scout/master/.claude/skills/open-ui-scout/SKILL.md" `
  -OutFile ".\.claude\skills\open-ui-scout\SKILL.md"
```

### 作为完整仓库克隆

如果你想同时保留 `README.md`、`AGENTS.md`、`AUDIT.md` 和贡献说明：

```bash
git clone https://github.com/underfitting-lu/open-ui-scout.git
cd open-ui-scout
```

Codex 也可以通过仓库根目录的 `AGENTS.md` 入口读取规则。

### Cursor / Windsurf / Gemini CLI

下载根目录公开版 `SKILL.md`，然后把它作为项目规则或 agent instruction 使用。

**macOS / Linux / Git Bash**

```bash
curl -L https://raw.githubusercontent.com/underfitting-lu/open-ui-scout/master/SKILL.md \
  -o OPEN_UI_SCOUT_SKILL.md
```

**Windows PowerShell**

```powershell
Invoke-WebRequest `
  -Uri "https://raw.githubusercontent.com/underfitting-lu/open-ui-scout/master/SKILL.md" `
  -OutFile ".\OPEN_UI_SCOUT_SKILL.md"
```

建议在项目规则中写明：

```text
Frontend UI tasks must read Open UI Scout first and output a short selection summary before implementation.
```

## 快速开始

1. 把 `SKILL.md` 或 `.claude/skills/open-ui-scout/SKILL.md` 放到 agent 能读取的位置。
2. 提出前端需求。
3. 要求 agent 先输出简短 selection summary。
4. 让 agent 最多使用 3 个主要 UI 来源完成实现。

## 示例 Prompts

```text
使用 Open UI Scout 重做这个 dashboard。先检查当前项目栈，再选择 base UI、dashboard 资源和 chart/table 资源。
```

```text
做一个温暖、舒服的登录页。不要黑紫科技风。先用 Open UI Scout 选择合适的开源 UI 资源。
```

```text
设计一个 AI Chat 工作台，包含 streaming、tool call、attachments、empty state 和 retry 状态。最多使用 3 个 UI 来源。
```

```text
设计一个 canvas editor workspace，包含左侧工具栏、中间画布、右侧属性面板、缩放控制和移动端适配。
```

## 风格判断规则

Open UI Scout 不会强行替用户决定风格：

- 用户明确说风格，就按用户说的来。
- 用户没说风格，但上下文很明显，agent 可以推断，但要在 selection summary 里说明假设。
- 用户没说风格，而且有多种可能，agent 应该先问，或给 2-3 个方向让用户选。

## 资源池覆盖范围

Open UI Scout 的资源池覆盖 707 个唯一 GitHub 仓库引用，分布在 16 个资源组，包括：

- React / Next.js / Vue / Nuxt / Svelte / Solid / Astro 等基础 UI 系统
- shadcn/ui 生态、registries、blocks
- Tailwind component blocks
- dashboard / admin templates
- landing page / marketing templates
- AI chat / agent UI
- editor / canvas / diagram workspace
- charts、tables、data visualization
- forms、uploads、payments、auth
- mobile H5 / native-style UI
- icons、fonts、design tokens
- testing、accessibility、quality tooling

## 常见候选 UI 资源示例

这些资源是 Open UI Scout 会参考或推荐 agent 去评估的候选来源，不代表本仓库打包、再分发或声明拥有它们。

| 场景 | 候选资源示例 |
| --- | --- |
| Base UI | [shadcn/ui](https://github.com/shadcn-ui/ui), [Radix UI](https://github.com/radix-ui/primitives), [Mantine](https://github.com/mantinedev/mantine), [Ant Design](https://github.com/ant-design/ant-design), [MUI](https://github.com/mui/material-ui), [HeroUI](https://github.com/heroui-inc/heroui) |
| Dashboard / Admin | [Tremor](https://github.com/tremorlabs/tremor), [TailAdmin](https://github.com/TailAdmin/free-nextjs-admin-dashboard), [Ant Design Pro](https://github.com/ant-design/ant-design-pro), [Tabler](https://github.com/tabler/tabler) |
| Landing / Blocks | [Magic UI](https://github.com/magicuidesign/magicui), [React Bits](https://github.com/DavidHDev/react-bits), [HyperUI](https://github.com/markmead/hyperui), [Preline](https://github.com/htmlstreamofficial/preline), [shadcnblocks](https://github.com/shadcnblocks/shadcn-ui-blocks) |
| AI Chat | [prompt-kit](https://github.com/ibelick/prompt-kit), [assistant-ui](https://github.com/Yonom/assistant-ui), [Vercel AI Chatbot](https://github.com/vercel/ai-chatbot), [Lobe Chat](https://github.com/lobehub/lobe-chat) |
| Editor / Canvas | [tldraw](https://github.com/tldraw/tldraw), [Excalidraw](https://github.com/excalidraw/excalidraw), [xyflow](https://github.com/xyflow/xyflow), [Konva](https://github.com/konvajs/konva), [Fabric.js](https://github.com/fabricjs/fabric.js) |
| Charts / Tables | [ECharts](https://github.com/apache/echarts), [Recharts](https://github.com/recharts/recharts), [TanStack Table](https://github.com/tanstack/table), [AG Grid](https://github.com/ag-grid/ag-grid) |
| Icons / Tokens | [Lucide](https://github.com/lucide-icons/lucide), [Tabler Icons](https://github.com/tabler/tabler-icons), [Phosphor Icons](https://github.com/phosphor-icons/core), [Radix Colors](https://github.com/radix-ui/colors), [Fontsource](https://github.com/fontsource/fontsource) |

## 第三方 UI 资源与许可证说明

Open UI Scout 本身使用 MIT License。见 [LICENSE](LICENSE)。

但资源池里提到的 UI 库、模板、blocks、图标、字体、动效库和工具都属于各自作者或组织，并受各自仓库的许可证约束。本仓库不会把这些第三方项目的源代码、模板或资产重新打包发布。

使用资源池时应遵守这些规则：

- 安装或复制任何第三方代码前，先检查对应仓库的 license。
- 如果 license 不清楚、仓库已归档、维护状态不适合生产使用，就不要作为依赖引入。
- 对模板、blocks、图标、字体和插画尤其要确认商用、署名、再分发和修改权限。
- 如果只是借鉴布局思路，也不要大段复制受版权保护的模板代码。
- 在项目 README、About、Credits 或 NOTICE 中按第三方 license 要求进行署名。

简单说：Open UI Scout 帮你“选择和判断”，不替代第三方 license 检查。

## 设计原则

- 先理解产品和页面，不从喜欢的 UI 库开始。
- 尊重用户明确指定的风格。
- 风格不明确时，先推断并说明假设；多种方向都合理时，先问或给选项。
- 尊重现有项目 UI 栈，不随便引入新体系。
- 每次最多选择 3 个主要 UI 来源。
- 不为了一个按钮或卡片引入大型 UI 库。
- 不默认黑紫科技风。
- 不混用过多视觉系统。
- 关注响应式、可访问性、状态完整性和可维护性。

## 反模式

- 所有页面都做成黑紫 AI 科技风
- 同一页混用 Ant Design、MUI、shadcn/ui、daisyUI、HeroUI
- 为了一个小组件安装大型 UI 库
- 把营销页动画塞进高密度 dashboard
- 忽略 license、维护状态、依赖成本和可访问性
- 未确认权限就复制大型模板或视觉资产

## 贡献

欢迎贡献新的 GitHub UI 资源、页面类型、style mode 或修复失效仓库。提交 PR 前请阅读 [CONTRIBUTING.md](CONTRIBUTING.md)。

---

<details id="english">
<summary><strong>English</strong></summary>

# Open UI Scout

Open UI Scout is a frontend UI resource selection skill for AI coding agents.

It helps an agent understand a frontend request, classify the page type and visual mood, inspect the current stack, and choose a small coherent set of open-source GitHub UI resources before generating code.

## What It Solves

AI coding agents often jump straight into one default style or one familiar UI library. Open UI Scout adds a decision layer first: understand the product, select resources that fit, then implement consistently.

## Workflow

```text
Understand request -> Classify page type -> Classify visual mood -> Inspect stack -> Score candidates -> Select up to 3 primary UI sources -> Generate consistent UI
```

## Who It Is For

- Developers using Codex, Claude Code, Cursor, Windsurf, Gemini CLI, or similar agents
- Builders who want stronger frontend taste from coding agents
- Teams that want agents to respect an existing UI stack
- Vibe coders who want varied styles instead of generic dark tech dashboards

## Install

Run one of the commands below. The default branch is `master`.

### Codex

**macOS / Linux / Git Bash**

```bash
mkdir -p ~/.codex/skills/open-ui-scout
curl -L https://raw.githubusercontent.com/underfitting-lu/open-ui-scout/master/.claude/skills/open-ui-scout/SKILL.md \
  -o ~/.codex/skills/open-ui-scout/SKILL.md
```

**Windows PowerShell**

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.codex\skills\open-ui-scout"
Invoke-WebRequest `
  -Uri "https://raw.githubusercontent.com/underfitting-lu/open-ui-scout/master/.claude/skills/open-ui-scout/SKILL.md" `
  -OutFile "$env:USERPROFILE\.codex\skills\open-ui-scout\SKILL.md"
```

Restart Codex after installation.

### Claude Code

Install into the current project:

**macOS / Linux / Git Bash**

```bash
mkdir -p .claude/skills/open-ui-scout
curl -L https://raw.githubusercontent.com/underfitting-lu/open-ui-scout/master/.claude/skills/open-ui-scout/SKILL.md \
  -o .claude/skills/open-ui-scout/SKILL.md
```

**Windows PowerShell**

```powershell
New-Item -ItemType Directory -Force ".\.claude\skills\open-ui-scout"
Invoke-WebRequest `
  -Uri "https://raw.githubusercontent.com/underfitting-lu/open-ui-scout/master/.claude/skills/open-ui-scout/SKILL.md" `
  -OutFile ".\.claude\skills\open-ui-scout\SKILL.md"
```

### Clone The Full Repository

```bash
git clone https://github.com/underfitting-lu/open-ui-scout.git
cd open-ui-scout
```

For Cursor, Windsurf, and Gemini CLI, download `SKILL.md` and use it as a project rule or instruction file.

## Style Decision Rule

- If the user explicitly names a style, follow it.
- If the user does not name a style but the context strongly implies one, infer the mood and state the assumption.
- If multiple moods are plausible, ask first or offer 2-3 directions before committing to resources.

## Third-Party UI Resources And Licenses

Open UI Scout itself is MIT licensed. The UI libraries, templates, blocks, icons, fonts, motion libraries, and tools mentioned in the resource pool belong to their respective authors and organizations.

This repository does not bundle, redistribute, or claim ownership of those third-party projects. Before installing, copying, or adapting any third-party code or asset, check the upstream repository license, maintenance status, and usage terms.

Open UI Scout helps agents choose and evaluate resources. It does not replace license review.

## Example Prompts

```text
Use Open UI Scout to redesign this dashboard. First inspect the current stack, then choose a base UI, dashboard resource, and chart/table resource.
```

```text
Build a warm cozy login page. Avoid dark AI tech style. Use Open UI Scout to pick suitable open-source UI resources first.
```

```text
Create an AI chat workspace with streaming states, tool-call states, attachments, and a polished composer. Use no more than 3 UI sources.
```

## License

MIT License. See [LICENSE](LICENSE).

</details>
