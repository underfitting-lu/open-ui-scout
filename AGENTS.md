# Open UI Scout Agent Guide

This repository contains **Open UI Scout**, a frontend UI resource selection skill for coding agents.

The primary skill file is:

```text
.claude/skills/open-ui-scout/SKILL.md
```

Before frontend UI, page design, component library selection, vibe coding, dashboard, landing page, AI chat, editor workspace, canvas, mobile UI, icon, token, or visual mood work, read the skill first.

When executing the skill:

- Understand the page type, product context, visual mood, technical stack, and production constraints before selecting resources.
- If the user names a style, follow it. If style is implied by context, state the assumption. If several styles are plausible, ask first or offer 2-3 directions.
- Inspect the existing project UI stack before introducing new libraries.
- Select from GitHub open-source UI resources only after scoring fit for stack, page type, mood, dependency cost, license clarity, and maintenance.
- Do not default to black-purple AI tech aesthetics.
- Do not mix too many UI libraries or visual systems.
- Use at most 3 primary UI sources per task.
- Do not introduce a large UI library for one isolated component.
- Output a short selection summary before generating UI unless the user explicitly asks for code only.
- Keep this skill general, public, and reusable when editing it.
