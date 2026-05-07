# Open UI Scout Skill Audit

## Overall Score

**91 / 100**

Open UI Scout is suitable for public sharing and practical vibe coding use after the automatic fixes in this repository. It has a clear decision workflow, a broad categorized GitHub resource pool, scoring criteria, anti-patterns, and agent-facing output contracts.

## Major Strengths

- Clear purpose: understand the frontend request first, then choose resources.
- Strong fit for vibe coding because it avoids one fixed visual style.
- Includes page type recognition, visual mood recognition, technical stack inspection, and production constraints.
- Includes 707 unique GitHub repository references across 16 resource groups.
- Resource pool is organized by category, including dashboard, landing page, AI chat, editor/canvas, mobile, icons, tokens, forms, testing, and accessibility.
- Includes candidate scoring criteria and a maximum of 3 primary UI sources per task.
- Includes explicit anti-patterns against black-purple default AI tech styling and over-mixing UI libraries.
- Can be executed by Codex, Claude Code, Cursor, Windsurf, Gemini CLI, and similar coding agents.

## Blocking Issues

None after the automatic fixes.

## Suggested Improvements

- Periodically verify the 707 repository references for moved, archived, or inactive projects.
- Consider splitting the large GitHub resource pool into reference files if the skill grows much further.
- Add a small "known moved or archived resources" section after doing a full GitHub verification pass.
- Add a few more compact recipes for mobile H5, settings pages, pricing pages, and docs pages.
- Add clearer guidance for projects that already use a strict enterprise design system.

## Automatically Fixed

- Added Codex-compatible YAML frontmatter with `name` and `description`.
- Added an explicit `Purpose` section.
- Added installation instructions for Claude Code and repository-level agent use.
- Added a Step 0 to understand page type, product context, visual mood, stack, and production constraints before choosing resources.
- Added a resource verification gate for repository existence, license, maintenance, stack match, dependency cost, and accessibility.
- Clarified that agents should inspect the existing project UI stack before adding libraries.
- Clarified that agents should not introduce a large UI library for a single isolated component.
- Clarified that agents should use at most 3 primary UI sources and avoid mixing full UI systems.
- Expanded the short decision summary to include current stack and dependency risk.
- Added `AGENTS.md`, `README.md`, `LICENSE`, `CHANGELOG.md`, `CONTRIBUTING.md`, `.gitignore`, and a lightweight GitHub Actions Markdown check.

## Still Needs Human Confirmation

- The resource pool contains 707 unique GitHub repository references. I checked the structure and counts locally, but I did not exhaustively verify every repository's current license, archival status, or maintenance activity.
- Some entries may require a future verification pass because they are known to have moved, been renamed, become archived, or have overlapping successors. Examples to re-check include `nextui-org/nextui`, `reactflow/react-flow`, `dnd-kit/docs`, `PuckEditor/puck`, `studio-freight/lenis`, and older template repositories.
- License compatibility must still be confirmed for the user's target project before installing or copying from any individual resource.
- Maintenance expectations depend on the task: stable but inactive template repositories may be acceptable as inspiration, while runtime dependencies should be actively maintained.

## Checklist Review

- Purpose: pass.
- When to Use This Skill: pass.
- Understand requirements before choosing libraries: pass.
- Page type recognition: pass.
- Visual mood recognition: pass.
- Technical stack recognition: pass.
- Existing project inspection: pass.
- GitHub open-source resource pool: pass.
- Category organization: pass.
- Candidate scoring: pass.
- Maximum 3 source rule: pass.
- Anti-patterns: pass.
- Avoid default black-purple tech style: pass.
- Avoid mixing too many UI libraries: pass.
- Dashboard, landing page, AI chat, editor/canvas, mobile, icons, tokens categories: pass.
- Public sharing suitability: pass.
- Markdown structure: pass after fixes.
- Suspicious repository spelling or existence: partial; requires periodic verification.
- License and maintenance reminders: pass after fixes.
- Agent executability: pass.

