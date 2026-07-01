---
name: iris
description: "Create editorial one-page HTML reports from AI analysis, research notes, codebase readings, technical explanations, and strategy memos, with a clear thesis, evidence path, useful diagrams, assumptions, open decisions, and next actions."
---

# Iris

Use Iris when a user wants AI analysis or agent output rendered as a refined single-page HTML report. Iris studies the material, identifies the report argument, chooses the right content mode inside the canonical report template, and produces a page that is visually compelling and comfortable to read.

Do not use Iris for resumes, slide decks, letters, portfolios, landing pages, UI kits, PDF-first documents, PPTX export, or generic website generation. Iris is narrower: it turns serious AI work into a report people can read, inspect, and act on.

## Inputs

Accept AI analysis, Markdown summaries, research notes, codebase findings, technical explanations, strategy memos, product judgments, decision notes, screenshots, prose notes, and agent-authored summaries.

Do not make users organize their thoughts into a structured data format. The agent reads the source material, identifies the thesis and evidence path, and composes the final HTML in the location that best fits the task.

Markdown may be used as a private working note while thinking through the report. It is not the delivery format and it is not a conversion contract. The final user-facing artifact is the completed HTML file.

Ask only for context that materially changes the report:

- intended reader
- desired decision or reaction
- must-include evidence
- anti-patterns or claims to avoid
- technical constraints
- preferred language

## Language Contract

Before composing, infer the report language from the user's request and source material. The default report language must match the user's language.

- If the user writes in Chinese, write the report in natural Chinese and set `{{LANG}}` to `zh-CN` unless they ask otherwise.
- If the user writes in English, write the report in natural English and set `{{LANG}}` to `en` unless they ask otherwise.
- Preserve source titles, product names, quoted text, API names, code identifiers, legal names, publication names, and evidence excerpts in their original language when translation would damage meaning or traceability.
- Do not mix interface labels, section headings, metadata labels, and closing headings across languages. If the body is Chinese, labels such as thesis, key findings, assumptions, and follow-through should also be Chinese. If the body is English, keep them English.
- When the source material is multilingual, choose one report language for the editorial voice, then mark original-language evidence as quoted or cited material.

## Report Template

Use `skills/iris/templates/report.html` as the canonical structure and style reference for every new creative report. Never ask the user to choose a template unless they explicitly care about implementation details.

Choose the content mode whose report personality matches the material:

| Mode | Role | Best for |
| --- | --- | --- |
| Standard analysis | Flagship analysis report. Strong first screen, key findings, evidence margins, precise figures. | AI summaries, codebase analyses, technical explanations, strategy memos, decision reports |
| Evidence-first | Research report. Observations, source synthesis, evidence-to-insight pairs, methodology notes. | Research findings, source synthesis, field notes, exploratory analysis |
| Position-led | Argument report. Strong claims, counter-arguments, principles, decision pressure. | Principles, critiques, strong stances, strategic declarations |

Decision tree:

```text
AI analysis, codebase reading, technical explanation, decision memo -> standard analysis
Research notes, source synthesis, observational material -> evidence-first
Strong stance, critique, principles, manifesto-like judgment -> position-led
Anything unclear but analytical -> standard analysis
```

## Template Slots

`report.html` accepts these slots:

- `{{LANG}}`: `en`, `zh`, or `zh-CN`
- `{{TITLE}}`: tight report title, ideally 10 words or fewer
- `{{HERO}}`: report opening with a text-only brand row, title, deck, thesis, and key findings
- `{{BODY}}`: report sections, evidence, figures, quotes, lists, and diagrams
- `{{CLOSING}}`: assumptions, open decisions or anti-patterns, and meaningful follow-through
- `{{FOOTER}}`: signature and slug

## Required Report Structure

Every Iris report should include:

1. **Thesis**: the central judgment or claim.
2. **Key findings**: 2 to 4 scan-friendly takeaways visible early.
3. **Evidence path**: sections that move from claim to support.
4. **Meaningful figures**: diagrams only when they clarify sequence, dependency, architecture, timeline, matrix, or decision paths.
5. **Assumptions**: what the report depends on.
6. **Open decisions or anti-patterns**: what remains unresolved or intentionally avoided.
7. **Follow-through**: concrete decisions, checks, or owner-facing moves that logically follow from the report.

If the source lacks any of these, infer responsibly from the material and label uncertainty in the closing.

## Content Method

Read `references/content-method.md` before composing a non-trivial report. Use it to turn raw material into an editorial argument:

- identify what the reader needs to understand or decide
- separate observation, inference, judgment, and uncertainty
- choose one defensible thesis
- select 2 to 4 key findings
- arrange sections as an evidence path, not a transcript
- write in the user's natural language
- mark assumptions and open decisions plainly

The report should sound like a careful person explaining the issue. Avoid filler, false certainty, model-like summary phrases, and vague improvement language.

## `report.html` Guidance

Use the Iris report vocabulary for all Iris output. The first screen should show:

- text-only brand row and date
- report title
- subtitle or executive framing
- lead paragraph
- thesis block
- key findings strip

The brand row should be typographic only. Do not add decorative logo SVGs, circular marks, image badges, or `.brand-mark` elements to generated reports unless the user explicitly asks for a specific brand asset.
Do not add a hero metadata strip for audience, scenario, evidence, constraints, or success criteria. That information belongs in prose, evidence notes, or the closing only when it materially helps the argument.

Body vocabulary:

- `.report-section`: main report section
- `.section-kicker`: section index or evidence type
- `.section-body`: title, lede, paragraphs, lists
- `.evidence-margin`: side evidence, compact notes, tags
- `.evidence-note`: concise sourced evidence or public record note
- `.side-note`: interpretive margin note or short quoted passage
- `.report-figure`: full-width figure plate
- `.matrix-wrap`: evidence matrix or comparison table wrapper
- `.findings-list`: numbered findings
- `.report-quote`: strong report emphasis

Use the standard analysis mode when in doubt.

All in-report links must open outside the report: use `target="_blank"` and `rel="noopener noreferrer"` on every `<a href="...">` unless the link is an internal page anchor.

## Evidence-First Guidance

Use an evidence-first report mode when the material is exploratory or source-heavy.

Body vocabulary inside `report.html`:

- `.report-section` for reading sections
- `.evidence-margin` for observations, source caveats, and method notes
- `.report-figure` for evidence plates
- `.findings-list` for evidence-to-insight pairs
- `.point-list` for compact observations

An evidence-first report should still close with assumptions and concrete follow-through.

## Position-Led Guidance

Use a position-led report mode when the material takes a strong stance.

Body vocabulary inside `report.html`:

- `.report-quote` for the central declaration
- `.findings-list` for numbered claims or principles
- `.point-list` for counter-arguments and rejected alternatives
- `.report-figure` for clarifying figures

The position-led mode should be bold, but not vague. It still needs evidence, assumptions, and concrete follow-through.

## Theme System

Use the built-in theme variables already embedded in `report.html`. The canonical Iris theme is the sharp editorial palette used by the shipped examples:

```css
--paper: #f4f2ed;
--surface: #fbfaf6;
--ink: #101010;
--muted: #66635e;
--line: #d3d0c7;
--accent: #545f80;
--accent-2: #a06f58;
--haze: #d8dbea;
```

Do not invent alternate palettes for ordinary reports. Accent colors should feel like faded ink, not neon.

## Diagram System

Diagrams are first-class evidence. Use them only when they explain:

- sequence
- dependency
- system boundary
- hierarchy
- tradeoff
- timeline
- decision path

Useful figure patterns:

- `flow`
- `architecture`
- `timeline`
- `matrix`
- `decision`

Build diagrams with the local template classes, semantic HTML, or inline SVG. Keep them portable and dependency-free.

## Evidence And Table System

Evidence margins and tables should look like the same editorial system, not imported widgets.

- Use `.evidence-note` for sourced facts, public records, measurements, and compact source caveats. Keep it short, label it clearly, and avoid heavy fills.
- Use `.side-note` for interpretive notes, narrow quotes, and contextual caveats. It should feel like a margin annotation, not a separate card.
- Do not stack visually unrelated evidence treatments in the same margin. Use the same accent line, label casing, and muted ink rhythm across the margin.
- Use `.matrix-wrap` around tables whenever the table is part of the argument. Tables should compare claims, risks, layers, decisions, or evidence. Avoid generic spreadsheet styling.
- Keep table headers short, align cells to the top, and write row labels as editorial categories rather than raw field names.
- On mobile, tables may scroll horizontally, but the wrapper must preserve readable padding, visible boundaries, and enough intrinsic table width for columns to remain legible.

## Chinese Typography

Chinese reports should feel intentionally typeset, especially when numbers, English product names, file paths, and code identifiers appear inside Chinese sentences.

- Use the template's CJK-aware font variables. For Chinese body prose, prefer the CJK serif chain already defined by `report.html`; for labels, dates, code, and compact evidence, use the sans or mono variables.
- Do not force Latin-first serif stacks into Chinese paragraphs. Mixed strings such as `HTML`, `PV`, `0731`, `API`, and `30%` should sit calmly inside the line instead of looking pasted in from another type system.
- Keep editorial labels, table headings, figure captions, assumptions, and follow-through headings in the report language. Preserve English only for product names, code, source titles, or terms whose identity would be damaged by translation.
- Do not insert brand marks or decorative symbols to make the first row feel branded. Let typography, date, report type, and evidence structure carry the identity.

## Closing Guidance

The closing is not a ritual "next steps" box. It should help the reader know what can be trusted, what remains unresolved, and what kind of follow-through is justified.

- Use three closing columns by default: assumptions, open decisions or anti-patterns, and follow-through.
- In Chinese reports, prefer headings such as `前提假设`, `待确认`, and `建议处理` or `后续验证`. Avoid the stiff label `下一步动作` unless the report is literally an execution plan.
- If there is no meaningful action, do not invent busywork. Use the final column for `复查点`, `观察窗口`, or `暂不行动的理由`, and make that choice explicit in the content.

## Workflow

1. Read the material.
2. Identify the reader, decision context, thesis, key findings, evidence, assumptions, and concrete follow-through.
3. Read `references/content-method.md` for any substantial report.
4. Set the language contract for the report and keep every editorial label in that language.
5. Choose the content mode inside `report.html`.
6. Compose the final report as self-contained HTML using the template's embedded theme.
7. Ensure every external link uses `target="_blank"` and `rel="noopener noreferrer"`.
8. Save it wherever the user request or local project context naturally expects the artifact.
9. Inspect the rendered page.
10. Refine the report structure before adding more style.

## Quality Bar

- The first screen should attract the eye and explain what judgment the report makes.
- A reader should understand the report structure in 10 seconds.
- Typography, spacing, and diagrams should carry meaning.
- Diagrams must clarify evidence, never decorate.
- The report must not look like a generic Markdown export, SaaS dashboard, or landing page.
- Body text must remain comfortable for sustained reading.
- Mobile output must not overflow horizontally.
- Generated HTML must be portable: embedded CSS, inline SVG, no remote dependencies.

## Completion

Before reporting completion after project edits, check that `report.html` remains usable as the canonical template reference and inspect at least one hand-authored HTML report at desktop and mobile widths. Use ad hoc local commands when helpful, but do not introduce a required conversion pipeline.

## References

- `references/design-system.md`: report visual system and quality guidance
- `references/content-method.md`: editorial extraction and writing method
- `references/test-method.md`: report test method
- `templates/report.html`: canonical analysis report template
