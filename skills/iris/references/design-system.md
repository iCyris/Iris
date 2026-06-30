# Iris Design System

Iris uses Editorial Intelligence: one canonical report template with flexible content modes for turning AI analysis into single-page HTML reading reports. The visual system should feel premium, analytical, and human-edited. It should attract the eye in the first screen, then make the evidence path easy to follow.

## Report Template

| Template | Role | Paper | Grid | Use |
| --- | --- | --- | --- | --- |
| `report.html` | Flagship analysis report | crisp editorial paper | 10-column report grid | AI summaries, codebase analysis, strategy memos, decision reports |

## Content Modes

| Mode | Use | Structure |
| --- | --- | --- |
| Standard analysis | AI summaries, codebase analysis, strategy memos, decision reports | Thesis, key findings, evidence sections, figures, closing |
| Evidence-first | Research notes, source synthesis, evidence to insight material | Observations, source caveats, evidence-to-insight pairs, method notes |
| Position-led | Strong stances, principles, critiques | Declarations, counter-arguments, decision criteria, next actions |

## Core Feeling

A high-quality analyst memo, a magazine feature, and a technical evidence report became one web-native artifact. The page should not feel like a generic document template. It should feel edited, paced, and specific to the analysis.

## First Screen Standard

The first screen must show:

1. What this report is about.
2. What judgment it makes.
3. Who it is for.
4. What evidence path the reader will follow.
5. A small set of key findings.

Strong display type is welcome, but it cannot crowd out the thesis or findings. The first screen should pull the reader in and orient them at the same time.

## Editorial Structure

The preferred report structure is:

1. Title and deck name the subject.
2. Lead opens the reading path.
3. Thesis states the central judgment.
4. Key findings make the report scannable.
5. Sections advance claim and evidence.
6. Figures clarify relationships near the claims they support.
7. Closing records assumptions, open decisions or anti-patterns, and next actions.

Do not treat every content object as an equal card. A strong Iris report has hierarchy: opening, judgment, evidence, figure, conclusion.

## System Consistency

Every supporting element should feel authored by Iris, not borrowed from another UI kit. Evidence margins, quoted notes, figures, tables, tags, and metadata should share the same material rules:

- thin rules instead of heavy boxes
- faded-ink accent lines instead of saturated fills
- small mono labels with the same casing rhythm
- quiet surface steps that do not compete with body text
- no generic SaaS cards, floating panels, or unrelated shadow treatments

If two evidence components sit near each other, they should differ by role, not by visual language. For example, `.evidence-note` can carry a source record and `.side-note` can carry interpretation, but both should use the same component skeleton: matching accent rule, line weight, label rhythm, muted ink tone, type family, padding, and surface treatment. Do not make one evidence block feel like a sans card and the next feel like a serif pull quote.

## HTML-First Rule

The finished artifact is a self-contained HTML report. Intermediate notes can be written in prose or Markdown while the agent thinks. Use the template as the canonical structure and style reference, then save the final HTML wherever the task naturally calls for it. Do not design the system around a separate conversion pipeline or structured input format.

## Composition

- Use a report sheet as the unit: folio, metadata, findings strip, evidence margins, and figure plates.
- Use typography, rhythm, and spatial contrast as structure.
- Keep information density high enough to feel like an analysis report.
- Let diagrams sit in the reading flow.
- Avoid low-density hero pages and generic card grids.
- Use whitespace as pacing, not empty decoration.

## Color

Palettes are defined as CSS custom properties pasted into `{{PALETTE}}`.

Every palette uses these variables:

```css
--paper
--surface
--ink
--muted
--line
--accent
--accent-2
--haze
```

Use one active accent per report. Accent colors should feel like faded ink. Avoid neon, saturated AI gradients, and one-note monochrome palettes.

## Typography

- Title: large, confident, and report-like. It should be a visual anchor, not a poster that eats the page.
- Body: quiet editorial reading type with enough line height for long passages.
- Metadata: small mono labels with tabular numbers.
- Findings: compact, high-contrast, scan-friendly.
- Chinese pages need calmer weight and more line height than Latin pages.
- Letter spacing remains `0` across the template.

Language and typography are linked. When the report is Chinese, translate the editorial labels and let the Chinese type scale breathe. When the report is English, keep labels English and avoid translated Chinese sentence rhythm. Preserve original-language evidence only when it has source value.

## Evidence Margins

Evidence margins are part of the reading argument. They should not look like detached cards.

- Use `.evidence-note` for sourced facts, public records, measurements, source caveats, and confidence notes.
- Use `.side-note` for short interpretive comments, quoted passages, or "why this matters" notes.
- Keep margin blocks compact. One margin block should usually prove or qualify one point.
- Use labels in the report language. Chinese reports should use labels like `公开记录`, `证据`, `限制`, or `说明`. English reports can use `Public record`, `Evidence`, `Limit`, or `Note`.
- Avoid mixed fills, mixed font families, mismatched line weights, or unrelated padding in one margin. Let the label text and content role create distinction inside a shared visual system.

## Tables

Tables should feel like evidence matrices, not raw spreadsheet exports.

- Wrap argumentative tables in `.matrix-wrap`.
- Use short column labels and top-aligned cells.
- Make the first column the row thesis or category, not an arbitrary field name.
- Prefer 3 to 5 columns. If more dimensions are needed, split the table or turn it into a figure.
- Keep rows separated by fine rules. Avoid heavy cell borders, zebra stripes, decorative shadows, and cramped padding.
- On mobile, allow horizontal scrolling inside the table wrapper rather than shrinking text until it becomes unreadable.

## Diagrams

Diagrams are evidence. They should explain:

- sequence
- dependency
- system boundary
- hierarchy
- tradeoff
- timeline
- decision path

Use thin strokes, compact captions, clear grouping, and labels that read as part of the report. Do not add diagrams for decoration.

## Motion

Generated HTML should work without JavaScript. If motion is added later, it must respect `prefers-reduced-motion` and stay subtle.

## Anti-Patterns

- Generic AI document templates.
- Landing page composition.
- Resume, slide, letter, or portfolio promises.
- Bootstrap, Ant-style UI, or dashboard chrome.
- Heavy card stacks with identical shadows.
- Decorative SVGs that do not clarify evidence.
- Dense paragraphs without thesis, findings, or next actions.
- Oversized display type that hides the report's point.
- Treating the report as a data transformation instead of an editorial composition.
