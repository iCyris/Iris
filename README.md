# Iris

<p align="center">
  <img src="assets/logo/generated/iris-mark-white.png" alt="Iris logo" width="180">
</p>

<h1 align="center">Iris</h1>

<p align="center">
  <strong>Turn AI analysis into editorial HTML reports.</strong>
</p>

Iris is a report layer for AI-assisted work. It takes analysis, research notes, codebase readings, product judgments, and technical explanations, then shapes them into a single self-contained HTML report.

It is not a document suite, landing page generator, slide template, or PDF workflow. Iris exists for one thing: turning serious AI output into a page someone can read, inspect, and act on.

## Examples

<p>
  <strong>English</strong><br>
  <img src="assets/readme/example-en.png" alt="English Iris report example">
</p>

<p>
  <strong>Chinese</strong><br>
  <img src="assets/readme/example-zh.png" alt="Chinese Iris report example">
</p>

## Use Iris For

- Codebase analysis reports
- Article summaries and interpretation
- Research notes and source synthesis
- Product or strategy judgments
- Technical explanations
- Requirements critique
- Thinking notes that need a clear conclusion

## How It Works

1. Read the source material.
2. Extract the thesis, findings, evidence, assumptions, open decisions, and next actions.
3. Compose a self-contained HTML report with the Iris template as the visual and structural reference.
4. Inspect the HTML at desktop and mobile widths.

Markdown can be useful as a private scratchpad while thinking. It is not the final deliverable. Iris delivers HTML.

## Core Files

| File | Purpose |
| --- | --- |
| `skills/iris/SKILL.md` | Main agent instructions |
| `skills/iris/references/content-method.md` | Content extraction and writing method |
| `skills/iris/references/design-system.md` | Visual system and report quality rules |
| `skills/iris/templates/report.html` | Canonical template reference |
| `examples/editorial-method.html` | Finished HTML example |
| `examples/editorial-method-zh.html` | Finished Chinese HTML example |

## Install

Iris is maintained as a local Codex plugin project.

```bash
codex plugin add iris@personal
```

For tools that do not use plugin metadata, start with:

```text
AGENTS.md
skills/iris/SKILL.md
```

## Project Layout

```text
Iris/
├── .codex-plugin/
├── assets/logo/generated/
├── assets/readme/
├── examples/
├── skills/iris/
│   ├── SKILL.md
│   ├── agents/
│   ├── assets/
│   ├── references/
│   └── templates/report.html
├── AGENTS.md
├── BRAND.md
├── CLAUDE.md
├── LOGO_SPEC.md
└── asset-manifest.json
```

## License

MIT License. See [LICENSE](LICENSE).
