# Iris Agent Guide

This file is the cross-agent entry point for Iris. Read it before editing project files or using the skill from an AI coding product.

## Purpose

Iris turns AI analysis, summaries, research notes, codebase readings, product judgments, and technical explanations into refined single-page HTML reports. The output should feel like a premium editorial analysis page: typography-led, evidence-aware, spatial, quiet, and immediately compelling.

Iris is not a landing-page generator, UI kit, slide template, resume maker, document suite, or PDF-first print system. It is a report layer for AI-assisted work: serious thinking shaped into a page people can read, inspect, and act on.

## Architecture

Iris is guided by one canonical report template: `skills/iris/templates/report.html`. An agent reads the material, identifies the report argument, chooses the right content mode, and composes a self-contained HTML report using Iris's visual vocabulary. The template is a source of structure and style, not a required output location. No rendering script runs between editorial judgment and the finished page for new creative work.

## Source Of Truth

- Canonical skill: `skills/iris/SKILL.md`
- Template library: `skills/iris/templates/report.html`
- Design guidance: `skills/iris/references/design-system.md`
- Content method: `skills/iris/references/content-method.md`
- HTML examples: `docs/examples/*.html`
- Logo assets: `assets/logo/generated/iris-mark-transparent.png`, `assets/logo/generated/iris-mark-white.png`
- Codex plugin metadata: `.codex-plugin/plugin.json`
- Claude Code guide: `CLAUDE.md`

Update the canonical skill and report template first, then sync root-level agent guides if workflow behavior changes.

## Language Policy

Project files, skill instructions, examples, durable deliverables, and generated handoff artifacts should be authored in English. Generated user-facing content may follow the user's requested language.

## Quality Bar

- Make the user's analysis more visible, not merely prettier.
- Every report should surface thesis, key findings, evidence, assumptions, open decisions, and meaningful follow-through.
- The first screen should attract attention while making the report's judgment and evidence path obvious.
- Use typography, spacing, rhythm, and diagrams as meaning-bearing structure.
- Avoid generic SaaS cards, ornamental gradients, and heavy UI chrome.
- Diagrams must clarify relationships, flows, or architecture, never decorate.
- Every output should include assumptions, open decisions, and meaningful follow-through in the closing. Do not invent a stiff "next actions" list when the material only justifies review points, observation windows, or a no-action rationale.
- Brand rows should be typographic. Do not add decorative brand marks, logo SVGs, circular badges, or `.brand-mark` elements unless a user explicitly asks for a specific brand asset.
- The HTML should be portable: embedded CSS, inline SVG, no remote dependencies.
- Content mode is an editorial act: evidence-first and position-led reports should still use `report.html`, but the writing pattern should match the material.

## Input Policy

Users should not have to organize their material into a structured data format. Iris accepts AI analysis, Markdown, prose, notes, screenshots, and agent-authored codebase analyses. The agent reads the material, identifies the report argument, and composes the final HTML where the task naturally calls for it. Markdown is allowed as a private scratchpad, but the final user-facing deliverable is HTML.

## Verification

Before reporting completion after project edits, check that `report.html` remains usable as the canonical template reference and inspect at least one hand-authored HTML report. When editing `report.html`, verify desktop and mobile rendering.

## Example Preview Workflow

When changing the report template, visual system, or example content:

1. Update both HTML examples: `docs/examples/editorial-method.html` and `docs/examples/editorial-method-zh.html`.
2. Capture fresh desktop preview images for README:
   - `assets/readme/example-en.png`
   - `assets/readme/example-zh.png`
3. Check the screenshots before committing. The first screen should feel clean, editorial, and readable in both English and Chinese.
4. Keep screenshots as final HTML previews. Do not introduce a structured input or conversion pipeline for examples.

## Git Hygiene

The worktree may contain user changes. Do not revert unrelated edits. Avoid destructive git commands.
