# Open UI Scout

Open UI Scout is a frontend UI resource selection skill for AI coding agents.

It helps an agent understand a frontend request, classify the page type and visual mood, inspect the current stack, and choose a small coherent set of open-source GitHub UI resources before generating code.

## What It Solves

AI coding agents often jump straight into one default visual style or one familiar UI library. Open UI Scout adds a decision layer first: understand the product, select resources that fit, then implement consistently.

It is especially useful when a prompt says things like "make this beautiful", "build a dashboard", "create a landing page", "make an AI chat UI", "design an editor workspace", or "use vibe coding".

## Who It Is For

- Developers using Codex, Claude Code, Cursor, Windsurf, Gemini CLI, or similar agents
- Designers and builders who want better frontend taste from coding agents
- Teams that want agents to respect existing UI stacks
- Vibe coders who want varied styles instead of generic dark tech dashboards

## Installation

Clone or download this repository, then copy the skill into the agent-specific skill location you use.

### Claude Code

Use this path inside a project:

```text
.claude/skills/open-ui-scout/SKILL.md
```

This repository already includes that structure.

### Codex

Codex can use the repository-level `AGENTS.md` entry. It points agents to:

```text
.claude/skills/open-ui-scout/SKILL.md
```

For frontend UI work, ask Codex to read Open UI Scout before choosing UI libraries or writing code.

### Cursor, Windsurf, Gemini CLI

Use the root `SKILL.md` or the `.claude/skills/open-ui-scout/SKILL.md` copy as a reusable rule file. Add a project instruction that says frontend UI tasks should first read Open UI Scout and output a short selection summary before implementation.

## Quick Start

1. Put `SKILL.md` or `.claude/skills/open-ui-scout/SKILL.md` where your agent can read it.
2. Ask for a frontend UI task.
3. Require a short selection summary before code.
4. Let the agent implement using at most 3 coherent UI sources.

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

```text
Design an editor workspace with a canvas, left toolbar, right properties panel, zoom controls, and responsive behavior.
```

## Resource Pool Coverage

Open UI Scout covers:

- base UI systems for React, Next.js, Vue, Nuxt, Svelte, Solid, Astro, and multi-framework projects
- shadcn/ui ecosystem registries and blocks
- Tailwind component blocks
- dashboard and admin templates
- landing and marketing templates
- AI chat and agent UI
- editor, canvas, diagram, and workspace libraries
- charts, tables, data visualization, forms, uploads, payments, auth, testing, accessibility, icons, fonts, and design tokens
- mobile H5 and native-style UI resources

## Design Principles

- Start from the product and page, not from a favorite library.
- Follow explicit style requests. When style is implied, state the assumption. When several styles are plausible, ask first or offer 2-3 directions.
- Respect the existing project stack.
- Select a small coherent set of resources.
- Score candidates for stack fit, page fit, mood fit, dependency cost, license clarity, maintenance, and accessibility.
- Use open-source resources as compatible dependencies or inspiration, not as blind copy-paste.
- Keep UI responsive, accessible, and production-aware.

## Anti-Patterns

- Defaulting every product to black-purple AI tech style
- Mixing Ant Design, MUI, shadcn/ui, daisyUI, and HeroUI in one page
- Installing a large UI system for one button
- Using marketing-page animation patterns inside dense dashboards
- Ignoring license, maintenance, accessibility, or mobile behavior
- Copying large templates verbatim without checking reuse rights

## License

MIT License. See [LICENSE](LICENSE).

## Contributing

Contributions are welcome. Please see [CONTRIBUTING.md](CONTRIBUTING.md) before adding repositories, page types, style modes, or workflow rules.
