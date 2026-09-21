---
name: personal-markdown
description: Write or revise Markdown documentation in the user's personal style, with topic-led arrow bullets, supporting dash points, separate example blocks, and sparse references to central concept notes. Use for knowledge-base notes and Markdown documentation across projects, or when refining this writing style; not merely because a chat response uses Markdown.
---

# Personal Markdown

Apply the user's writing conventions so notes are easy to skim in both raw edit mode and rendered preview. These symbols carry meaning; do not replace them with preview-oriented prose formatting.

## Scope

- Apply to Markdown documentation being created or substantively revised. Keep small edits focused; do not reformat an entire file or repository without a task that calls for it.
- Follow the user's current instructions and required project formats when they differ from this default. Keep project-specific paths, topic ownership, and folder conventions in that project's instructions.
- Use filenames, folders, and headings to convey intent. Do not add README files or navigation infrastructure just to explain a knowledge base. Preserve required project READMEs and templates; explicit requests to write them take precedence.

## Topic and supporting points

- Prefer short, topic-led headings such as `Prompt and context` or `smallest approach`. Let the heading establish the subject without repeating it in a generic introductory bullet.
- Use `* ->` for direct definitions, responsibilities, distinctions, and other main points. A complete statement can follow the arrow; do not force every point into a standalone topic label followed by an explanation.
- Use following unindented `-` lines for supporting reasons, qualifications, or examples when a main point needs elaboration. A topic-only arrow bullet remains useful for a group of supporting points.
- Use ordinary bold for key terms and phrases a reader should notice while skimming. Reserve bold inline code for especially important concepts or precise phrases, including within a sentence; it is not mandatory on every topic label.
- Keep one coherent idea together: combine closely related responsibilities or dependencies in one arrow statement using `+`, `&`, or a clear progression. Split when each phase, action, failure kind, or condition needs separate attention; compactness does not mean packing a paragraph into one bullet. Preserve conditions, sequence, and distinctions that affect meaning.
- Place general definitions and qualifications with the concept before its example. Use `* =>` for an actual consequence or takeaway, not merely for a general statement placed after an example.
- Emphasize the key term, contrast, or failure condition within a statement rather than bolding whole sentences. Avoid repeating emphasis already supplied by the heading.
- Reduce tutorial narration and redundant reassurance. State the concept or readiness criterion directly, and use headings to organize concepts rather than narrate the reading journey.
- Avoid formulaic **Why**, **Problem**, **Example**, and **Next** labels attached to every point. Explain the reason naturally under its topic.
- Preserve `* =>` for consequences, takeaways, or relevant reference lines where appropriate. Preserve meaningful uses of `*`, `>`, underscores, and other local symbols without inventing new semantics for them.
- Put a local qualification or supplementary explanation in `(_..._)`. Use separate `* _..._` or `- _..._` lines for secondary notes, prerequisites, level, terminology keys, or references applying to the section. Place this context after the main overview when that makes the subject easier to grasp. Do not give every aside the same visual weight as the main arrow statements.
- Under explanatory headings such as The problem, use short plain `-` points rather than prose paragraphs. Use `* ->` for the main technical statements or actions. Add a shared heading such as Building blocks when several sibling sections contain the same kind of material; avoid a separate heading for a single takeaway that belongs beside the preceding table.
- Prefer visible explanations and worked answers in the note flow. Do not add HTML details/summary wrappers unless requested or required by the format. Avoid repeating fictional-data or setup caveats already made clear nearby.
- Prefer numerals for compact counts such as 3 scenarios or 4 decisions; emphasize the important concept rather than the count.
- Use `=========================================================` separators at major topic or phase boundaries; sibling subsections normally rely on their headings rather than a separator before each one. Prefer separating a term from its explanation with a line break, dash, or arrow over forcing colon-heavy definitions.
- Keep useful tables, diagrams, and code. Do not force every kind of document into a rigid topic template.

## Examples and code

- Visually separate illustrative scenarios from general knowledge with a `yml` fence starting with `# Example: <scenario>`. Put the scenario on that header line when concise, and use `->` for its component statements or steps. This is the user's visual convention; the prose inside need not be executable YAML.
- Group related extended examples beneath a heading such as `# Example: request pipeline`, with the particular applications as subheadings. Remove adjacent miniature examples that merely repeat the scenario or diagram.
- Split long example sentences into meaningful lines. Do not insert Markdown emphasis inside a code fence expecting it to render.
- Use appropriate language fences for actual code. Label mixed non-executable pseudocode explicitly and use `text`; do not label it runnable Python.
- Distinguish illustrative snippets from executed examples. Document prerequisites when providing runnable exercises.

## Knowledge ownership and references

- Find the existing central concept note before adding general explanations elsewhere. Keep the general knowledge for an aspect there; context-specific notes reference it and add their own applied detail.
- Avoid automatic backlinks from a central note to every application, sequential next-reading chains, and duplicate introductions. References should explain a relevant dependency or related aspect, not create navigation for its own sake.
- Keep references compact: use an inline parenthetical for a local dependency, `* =>` lines for section reference groups, or a secondary italic line for a contextual reference. A standalone `>` remains appropriate for a single related note. Avoid dense `> Read:` paragraphs: split distinct reference groups across lines and join closely related paths with `+`.
- Prefer the user's raw-text `bash` fences for comparison and exercise tables, including small tables. This is a presentation convention, not executable shell; ordinary Markdown tables remain appropriate when the local example or required format calls for them. When a table needs references, prefer a shared `# see` line above it over a repeated Read column. Keep column counts consistent and avoid adding Markdown emphasis inside new fenced tables. Choose directory references when they sufficiently identify the owning area.
- Prefer simple text references using the project's path conventions. Do not convert them into clickable Markdown links. In knowledge bases that use `~/...`, it means the knowledge-base root, not necessarily the operating-system home directory.
- Use a supporting point such as `- ~/concepts/evaluation.md (_measurement concepts_)`, or put the path beside its relevant point as `(_~/concepts/evaluation.md_)`. These are illustrative paths, not files to create.
- Check actual targets. Do not reproduce path typos from a style example or introduce this skill's sample paths into a real project.

## Before and after

Before:

````text
* -> **`Evaluation`** - measure performance on defined tasks and criteria
* -> **Why** - one convincing answer cannot establish overall quality
* -> **Example** - compare two prompts on the same support questions

> Next - another pattern; another application
````

Preferred:

````markdown
* -> **`Evaluation`**
- measure how well an AI system performs on a **defined set of tasks and criteria**
- one convincing answer cannot tell you whether a prompt change improves the whole system

```yml
# Example:
run the same 50 support questions before and after a prompt change;
compare answer quality, task completion, and latency
```

* -> **`What to measure`**
- choose criteria that reflect the task (_answer quality, task completion, latency_)
````

Direct statements under a topic heading are also preferred when no supporting group is needed:

```markdown
## Prompt and context
* -> **prompt** tells the model what to do
* -> **context** supplies information for the request
* -> **application** supplies information + handles the response + controls access to other systems

* => choose an approach from **the information available and the action required**
```

These examples illustrate flexible layouts, not a mandatory heading sequence or a requirement to give every arrow bullet supporting lines. Preserve deliberate raw-text layouts, including the fenced comparison-table convention above, without reproducing accidental syntax errors or treating every table as necessarily fenced.

## Refine this skill

- When the user provides another style explanation, update this skill's relevant rule and, when useful, its example. Maintain one source of truth rather than copying the full style into project AGENTS.md files.
- Apply clear refinements directly. If a new preference conflicts with an earlier rule and the intended distinction remains unclear, ask a focused question before changing that rule; continue independent work.
- Distinguish reusable preferences from project-specific exceptions. Do not generalize every one-off example into a universal rule.
- Check edits for preserved meaning, topic/support hierarchy, example separation, valid reference targets, and balanced fences. Use the skill-creator validator when changing skill structure or metadata.
