# Iris Content Method

Iris is an editorial method before it is a visual template. The agent's job is to turn messy source material into a clear report argument, then compose a self-contained HTML report using the Iris template as a structural and visual reference.

Markdown can be used privately as a scratchpad while thinking. It is not a user-facing input contract, not a conversion format, and not the final deliverable. The final artifact is a self-contained `.html` report.

## Core Loop

1. Read the material.
2. Name the user's real situation: what they are trying to understand, decide, explain, or improve.
3. Separate observation, inference, judgment, and uncertainty.
4. Choose one thesis the report can defend.
5. Select 2 to 4 key findings that make the thesis scannable.
6. Build an evidence path: sections, margin notes, quotes, lists, and figures.
7. Set the report language from the user's language unless the user asks for another language.
8. Write in the user's natural language. Use direct, human sentences.
9. Compose the final HTML with the report template classes.
10. Open the HTML and revise the reading rhythm before delivery.

## Language Discipline

The editorial voice, section labels, metadata labels, figure captions, table headers, assumptions, open decisions, and next actions should use the same language as the user's request by default.

Allowed exceptions:

- product names, organization names, project names, API names, identifiers, and filenames
- direct quotes or source titles where the original language matters
- citations whose wording should remain traceable to the source
- bilingual reports explicitly requested by the user

When an exception appears, make it feel intentional. Do not leave English labels such as "Thesis", "Key findings", "Assumptions", or "Next actions" inside an otherwise Chinese report. Do not translate code, package names, command names, or source titles that would become less identifiable after translation.

## Editorial Standards

- Do not dump notes. Extract the signal.
- Do not pretend certainty. Mark what is known, inferred, unknown, or unresolved.
- Do not make vague claims like "improve efficiency" unless the source supports a concrete meaning.
- Do not pad the report with generic AI summary language.
- Do not flatten disagreement. If the material contains tension, make the tension visible.
- Do not treat all bullets equally. Promote only the bullets that change the reader's understanding.
- Do not force diagrams. Add a figure only when it clarifies sequence, dependency, hierarchy, tradeoff, timeline, or decision path.

## Writing Voice

Use plain language with judgment. The report should sound like a careful person explaining what matters, not like a model summarizing a prompt.

Prefer:

- "The risk is not the API call itself. The risk is that retry state is hidden from the checkout page."
- "The article proves the pattern exists, but not that it is durable."
- "This requirement is underspecified: it names the desired feeling, not the behavior that creates it."

Avoid:

- "This comprehensive analysis explores various aspects."
- "It is important to note that..."
- "This feature will significantly enhance user experience."
- "The data clearly shows..." when the evidence is incomplete.

## Scenario Patterns

### Codebase Analysis

Start from the maintainer's decision, not the file tree. Read the relevant files, name the boundary, cite paths in prose, and use diagrams for ownership or flow. End with risks, assumptions, and verification steps.

### Article Or Research Summary

Separate what the source says from what it implies. Preserve important claims, surface weak evidence, and add context only when it is clearly labeled. A good report helps the reader decide how much trust to place in the source.

### Current Events Or Situation Breakdown

Use dates, actors, incentives, known facts, disputed facts, and unknowns. Avoid moral fog and avoid invented motives. If fresh facts matter, verify them before writing.

### Thinking Or Personal Notes

Find the unresolved question. The report should help the user see their own thinking more clearly: what they believe, what they are avoiding, what would change their mind, and what action is now possible.

### Requirement Or Product Evaluation

Judge the requirement, not only its implementation. Name the user, job, success condition, cost, risk, and anti-pattern. If the requirement is vague, clarify what must become concrete before implementation.

## Report Anatomy

Every final HTML report should include:

- Opening: subject, reader, source context, thesis, and key findings.
- Body: evidence sections arranged in a deliberate reading order.
- Figures: optional, but meaningful when used.
- Closing: assumptions, open decisions or anti-patterns, and next actions.

## Links And Source Access

External links should preserve the report as the reader's home surface. Every external `<a>` must include `target="_blank"` and `rel="noopener noreferrer"`. Internal anchors may stay in the same page.

Use margin evidence for compact source context, not for dumping URLs. A useful source note names what the source proves, what it does not prove, and how it affects the report's judgment.

## Final Deliverable Rule

The final file is HTML. It should be portable, embedded, readable on mobile, and polished enough to hand to another person without explaining the process that produced it.
