# Iris For Claude Code

Use Iris when the user wants AI analysis, summaries, codebase readings, research notes, technical explanations, strategy judgments, or decision memos rendered as a polished single-page HTML report.

Do not use Iris for resumes, slide decks, letters, portfolios, landing pages, PDF-first documents, or general website generation.

## First Files To Read

1. `skills/iris/SKILL.md`
2. `skills/iris/references/content-method.md`
3. `skills/iris/references/design-system.md`
4. `skills/iris/templates/report.html`

## Working Pattern

1. Read the source carrier: AI analysis, Markdown, notes, screenshot observations, or an agent-authored codebase analysis.
2. Identify the report thesis, key findings, evidence path, assumptions, open decisions, and meaningful follow-through.
3. Use `content-method.md` to separate observation, inference, judgment, and uncertainty.
4. Use `report.html` as the structure and style reference. Choose the content mode inside the report: standard analysis, evidence-first research, or position-led argument.
5. Choose a palette from `SKILL.md` or compose a custom palette using the same CSS variable names.
6. Compose the final report as self-contained HTML using Iris's CSS classes and visual vocabulary.
7. Save the HTML wherever the user request or local project context naturally expects the artifact.
8. Inspect the HTML output before delivery. The first screen must make the report's judgment and evidence path visible without adding a metadata strip.
9. Refine by adjusting content, structure, or palette. Do not hand-edit template CSS for one-off content changes.

## Output Standard

The page should feel like a premium editorial analysis report, not a component demo or generic document template. Prefer strong hierarchy, restrained color, precise diagrams, evidence notes, exact copy, and a reading rhythm that leads from thesis to evidence to justified follow-through. Keep the brand row typographic; do not add decorative brand marks or logo SVGs unless the user explicitly asks for one.

## Report Mode Quick Reference

| Mode | Personality | Best for |
| --- | --- | --- |
| Standard analysis | Flagship report with evidence margins and key findings | AI summaries, codebase analysis, technical explanations, strategy memos |
| Evidence-first | Research report with observations, source synthesis, and evidence-to-insight pairs | Research notes, field findings, exploratory analysis |
| Position-led | Strong argument with declarations, counter-arguments, and decision pressure | Principles, critiques, strong product or technical stances |

`report.html` documents the canonical slots: `{{LANG}}`, `{{TITLE}}`, `{{PALETTE}}`, `{{HERO}}`, `{{BODY}}`, `{{CLOSING}}`, `{{FOOTER}}`.

Markdown may be used as a private scratchpad, but it is not the final deliverable. Iris delivers a self-contained HTML report.
